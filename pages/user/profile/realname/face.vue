<template>
    <view class="body">
        <view class="input-group inner">
            <view class="input-row border input-flex">
                <label class="title">{{$t('user.geRenZhengJian')}}</label>
                <view class="flex1 input-flex" @tap="onFrontSelect">
                    <image class="card" src="../../../../static/img/card_front.png" mode="center"></image>
                    <label class="inner">{{frontImg==''?$t('common.front'):$t('common.hasSelect')}}</label>
                </view>
                <view class="flex1 input-flex" @tap="onReverseSelect">
                    <image class="card" src="../../../../static/img/card_front.png" mode="center"></image>
                    <label class="inner">{{backImg==''?$t('common.reverse'):$t('common.hasSelect')}}</label>
                </view>
            </view>
            <view class="input-row border input-flex">
                <label class="title long">{{$t('user.renLianShiBie')}}</label>
                <view class="flex1  input-flex" @tap="onFaceSelect">
                    <view class="input-flex">
                        <uni-icons type="scan"></uni-icons>
                    </view>
                    <label class="inner">{{facePath==''?'':$t('common.hasSelect')}}</label>
                </view>
            </view>
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
            return {
                btnDisabled: true,
                faceStatus: '',
                frontImg: "",
                backImg: "",
                faceImg: "",
                facePath: "",
                loadFront: false,
                loadBack: false,
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

                if (util.isAuth(that.auth.idState) && util.isAuth(that.auth.faceState)) {
                    util.confirm(that.$t('user.zhengShiXingMing') + that.$t('tip.yiRenZhengShiFouChongXiuRenZheng'), function () {
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
                that.saveFaceAuth(function (obj2,msg,code) {
                    util.tip(msg || (that.$t('common.certitrue')), {
                        over() {
                            uni.redirectTo({
                                url: '../profile'
                            });
                        }
                    });
                });
            },
            onFrontSelect() {
                var that = this;
                uni.chooseImage({
                    count: 1,
                    sizeType: ['compressed'],
                    sourceType: ['camera'],
                    success: function (res) {
                        const filePath = res.tempFilePaths[0];
                        var input = {
                            userId: that.userId,
                            name: "frontImg",
                            file: filePath,
                            filePath: ""
                        };
                        that.loadFront = true;
                        userService.saveFaceauth(input, function (obj, msg, code) {
                            that.frontImg = JSON.stringify(msg);
                            that.loadFront = false;
                        });
                    }
                });
            },
            onReverseSelect() {
                var that = this;
                if (that.loadFront) {
                    util.tip(that.$t('tip.wait'))
                    return;
                }
                if (util.isEmpty(that.frontImg)) {
                    util.tip(that.$t('tip.qingShangChuanZhengJianZhengMianZhaoPian'))
                    return;
                }
                uni.chooseImage({
                    count: 1,
                    sizeType: ['compressed'],
                    sourceType: ['camera'],
                    success: function (chooseImageRes) {
                        const filePath = chooseImageRes.tempFilePaths[0];
                        var input = {
                            userId: that.userId,
                            name: "backImg",
                            file: filePath,
                            filePath: "{'filePath':[" + that.frontImg + "]}"
                        };
                        that.loadBack = true;
                        userService.saveFaceauth(input, function (obj, msg, code) {
                            that.backImg = JSON.stringify(msg);
                            that.loadBack = false;
                        });
                    }
                });
            },
            onFaceSelect() {
                var that = this;

                if (that.loadBack) {
                    util.tip(that.$t('tip.wait'))
                    return;
                }

                if (util.isEmpty(that.frontImg)) {
                    util.tip(that.$t('tip.qingShangChuanZhengJianZhengMianZhaoPian'))
                    return;
                }

                if (util.isEmpty(that.backImg)) {
                    util.tip(that.$t('tip.qingShangChuanZhengJianFanMianZhaoPian'))
                    return;
                }

                uni.chooseImage({
                    count: 1,
                    sizeType: ['compressed'],
                    sourceType: ['camera'],
                    success: function (chooseImageRes) {
                        that.facePath = chooseImageRes.tempFilePaths[0];
                    }
                });
            },
            getAuth(callback) {
                var that = this;
                userService.auth({ userId: that.userId }, function (obj, msg, code) {
                    that.faceStatus = status.faceState;
                    if (util.isFunction(callback)) {
                        callback(obj);
                    }
                })
            },
            saveFaceAuth(callback) {
                var that = this;
                if (util.isEmpty(that.frontImg)) {
                    util.tip(that.$t('tip.qingShangChuanZhengJianZhengMianZhaoPian'))
                    return;
                }
                if (util.isEmpty(that.backImg)) {
                    util.tip(that.$t('tip.qingShangChuanZhengJianFanMianZhaoPian'))
                    return;
                }
                var input = {
                    userId: that.userId,
                    name: "sdkImg",
                    file: that.facePath,
                    filePath: "{'filePath':[" + that.frontImg + "," + that.backImg + "]}"
                };

                userService.saveFaceauth(input, function (obj, msg, code) {
                    that.faceImg = JSON.stringify(msg);
                    if (util.isFunction(callback)) {
                        callback(obj);
                    }
                }, null, {
                    loading: that.$t('tip.zhengZaiShiBie')
                });
            },
        },
        onLoad: function () {
            var that = this;
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

