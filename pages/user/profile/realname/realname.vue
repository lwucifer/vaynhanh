<template>
    <view class="body">
        <view class="input-group inner">
            <view class="input-row border input-flex">
                <label class="title">{{$t('user.zhengShiXingMing')}}</label>
                <m-input type="text" :placeholder="$t('tip.qingShuRuZhengShiXingMing')" v-model="name"></m-input>
            </view>
            <view class="input-row border">
                <label class="title">{{$t('user.shenFenZhengHao')}}</label>
                <m-input type="number" :placeholder="$t('tip.qingShuRuShenFenZhengHao')" v-model="idcard"></m-input>
            </view>
            <view class="input-row border">
                <label class="title long">{{$t('user.chuShengRiQi')}}</label>
                <view class="input-flex flex1" @click="onBirthdayShow"> {{birthday}} </view>
                <mPicker ref="birthdayPicker" mode="dateSelector" :pickerValueDefault="new Date(birthday)"  @onConfirm="onBirthdayConfirm"></mPicker>
            </view>
            <view class="input-row border">
                <label class="title">{{$t('user.xingBie')}}</label>
                <view class="input-flex flex1" @click="onSexShow"> {{sex}} </view>
                <mPicker ref="sexPicker" mode="selector" :pickerValueArray="sexs" :pickerValueDefault="[sexIndex]"  @onConfirm="onSexConfirm"></mPicker>
            </view>
        </view>
        <view class="input-line inner">
            <label class="inline">
                <text>{{$t('user.shiMingXingXiTiShi1')}}</text>
            </label>
        </view>
        <view class="input-line inner">
            <button type="primary" class="primary" @tap="onApply" :disabled="btnDisabled">{{$t('common.certiapply')}}</button>
        </view>
    </view>
</template>

<script>
    import {
        mapState,
        mapMutations
    } from 'vuex'

    import uniIcons from "@/components/uni-icons/uni-icons.vue"
    import mPicker from "@/static/components/m-picker/m-picker.vue"
    import mInput from '@/static/components/m-input.vue'
    import mCode from '@/static/components/m-code.vue';

    import util from '@/util/util.js'
    import appService from '@/services/application.js'
    import userService from '@/services/user.js'

    export default {
        data() {
            var that = this;
            var nowDt = new Date();
            var sexs = util.toPickers([
                util.SELECTFIRST(),
                { code: '1' , value: that.$t('common.sex1')},
                { code: '2' , value: that.$t('common.sex2')}
            ]);
            return {
                name: '',
                idcard: '',
                sexs: sexs,
                sex: that.$t('tip.qingXuanZe') + '',
                sexIndex: 0,
                birthday: (nowDt.getFullYear() + "-" + (nowDt.getMonth() + 1) + "-" + nowDt.getDate()),
                btnDisabled: true,
            }
        },
        components: {
            uniIcons,
            mPicker,
            mInput,
            mCode
        },
        computed: {
            ...mapState(["userId", "auth"])
        },
        methods: {
            ...mapMutations(["pageAuth"]),
            onInit() {
                var that = this;
                that.faceStatus = that.auth.faceState;

                var _load = function () {
                    that.btnDisabled = false;
                }

                if (util.isAuth(that.auth.idState) && util.isAuth(that.auth.realNameState)) {
                    util.confirm(that.$t('user.zhengShiXingMing') + ' ' + that.$t('tip.yiRenZhengShiFouChongXiuRenZheng'), function () {
                        _load();
                    }, function () {
                        uni.redirectTo({
                            url: '../profile'
                        });
                    })
                } else {
                    _load();
                }
            },
            onApply() {
                var that = this;
                that.saveRealName();
            },
            onBirthdayShow(e) {
                var that = this;
                that.$refs.birthdayPicker.show(new Date(that.birthday));
            },
            onBirthdayConfirm(e) {
                var that = this;
                that.birthday = e.label
            },
            onSexShow(e) {
                var that = this;
                that.$refs.sexPicker.show([that.sexIndex]);
            },
            onSexConfirm(e) {
                var that = this;
                that.sexIndex = parseInt(e.value[0]);
                that.sex = that.sexs[that.sexIndex]["label"];
            },
            getAuth(callback) {
                var that = this;
                userService.auth({ userId: that.userId }, function (obj, msg, code) {
                    that.faceStatus = status.faceAuth;
                    if (util.isFunction(callback)) {
                        callback(obj);
                    }
                })
            },
            saveRealName() {
                var that = this;
                userService.saveRealname({ ...that.$data, userId: that.userId }, function (obj, msg, code) {
                    util.tip(msg || (that.$t('common.certitrue')), {
                        over() {
                            uni.redirectTo({
                                url: '../profile'
                            });
                        }
                    });
                });
            }
        },
        onLoad: function () {
            var that = this;
            //�����յ���ҳ�淵��ʱ��������
            userService.get({ userId: that.userId }, function (obj, msg, code) {
                that.name = obj.realName;
                that.idcard = obj.idNo;
                that.birthday = obj["birthday"] || that.birthday;
                for (var i = 0; i < that.sexs.length; i++) {
                    if (that.sexs[i] == obj.sex) {
                        that.sexIndex = i;
                        that.sex = obj.sex;
                    }
                }
            })
        },
        onShow: function () {
            var that = this;
            that.pageAuth({ callback: that.onInit });
        }
    }
</script>
<style>
    .card {
        width: 42upx;
        height: 42upx;
        padding-left: 5upx;
    }
</style>

