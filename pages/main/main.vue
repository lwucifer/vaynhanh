<template>
    <view class="body">
<!--        <swiper class="swiper flex1" indicator-dots="true" autoplay="false" interval="2000" duration="500">-->
<!--            <swiper-item>-->
<!--                <image class="img-view" src="../../static/img/bg.png"></image>-->
<!--            </swiper-item>-->
<!--        </swiper>-->
        <view class="home">
            <h1>{{ $t('common.title') }}</h1>
            <navigator url="../content/help/help" class="icon-help">
                <uni-list-item :title="$t('common.helper')" show-extra-icon="true" :extra-icon="{type: 'help'}">
                    <img src="../../static/img/help.png"/>
                </uni-list-item>
            </navigator>
            <img class="img-view" src="../../static/img/bg.png"/>
            <div class="bottom">
                <view class="tools d-flex">
                    <button @click="minus()" :disabled="check_min">-</button>
                    <span>{{ quotaShow }}<br/><span>{{ $t('common.currency2') }}</span></span>
                    <button @click="plus()" :disabled="check_max">+</button>
                </view>
                <button type="primary" class="primary apply btn" @tap="onBorrowing">{{ $t('common.apply') }}</button>
            </div>
        </view>
        <!--        <a href="../../static/shortcut/Vaynhanh.mobileconfig" class="btn">link link</a>-->
        <!--        <view><uni-notice-bar show-icon="true" single="true" :text="notice"></uni-notice-bar></view>-->
    </view>
</template>

<script>
    import {
        mapState,
        mapMutations
    } from 'vuex'

    import uniIcons from "@/components/uni-icons/uni-icons.vue"
    import uniNoticeBar from "@/components/uni-notice-bar/uni-notice-bar.vue"
    import uCharts from '@/components/u-charts/u-charts.js';

    import util from '@/util/util.js'
    import appService from '@/services/application.js'
    import busService from '@/services/business.js'

    export default {
        data() {
            return {
                notice: "",
                borrowingArcbar: null,
                borrowingArcbarWidth: uni.upx2px(380), //这里要与样式的宽高对应
                borrowingArcbarHeight: uni.upx2px(380), //这里要与样式的宽高对应
                arcbarWidth: uni.upx2px(20), //圆弧进度图，进度条宽度,此设置可使各端宽度一致
                pixelRatio: 1,
                check_min: false,
                check_max: false,
                quotaTemp: 1000000,
                quotaShow: '1,000,000',
                min: 500000,
                max: 2000000,
                diff: 100000,
            }
        },
        components: {
            uniNoticeBar
        },
        computed: {
            ...mapState(["isLogin", "auth","userId","userName", "quota", "borrow"])
        },
        methods: {
            ...mapMutations(["pageView", "canBorrowing"]),
            onInit() {
                var that = this;
                var Arcbar1 = {
                    series: [{
                        "name": that.$t('bus.eDu') + ' ' + util.toMoney(that.quota) + " " + that.$t('bus.yuan'),
                        "data": (that.borrow / that.quota).toFixed(2),
                        "color": "#2fc25b"
                    }]
                };
                that.quotaTemp =  that.quota;
                that.checkQuota();
                //that.showArcbar(Arcbar1);
            },
            minus () {
                const that = this;
                if (that.quotaTemp > that.min) {
                    that.quotaTemp = that.quotaTemp - that.diff;
                }
                that.checkQuota();
            },
            plus () {
                const that = this;
                if (that.quotaTemp < that.max) {
                    that.quotaTemp = that.quotaTemp + that.diff;
                }
                that.checkQuota();
            },
            checkQuota () {
                const that = this;
                that.quotaShow = util.toMoney(that.quotaTemp);
                that.check_max = that.quotaTemp >= that.max;
                that.check_min = that.quotaTemp <= that.min;
            },
            showArcbar(data) {
                var that = this;
                that.borrowingArcbar = new uCharts({
                    $this: that,
                    canvasId: "borrowingArcbar",
                    type: 'arcbar',
                    fontSize: 11,
                    legend: {
                        show: false
                    },
                    background: '#FFFFFF',
                    pixelRatio: that.pixelRatio,
                    series: data.series,
                    animation: true,
                    width: that.borrowingArcbarWidth * that.pixelRatio,
                    height: that.borrowingArcbarHeight * that.pixelRatio,
                    dataLabel: true,
                    title: {
                        name: Math.round(data.series[0].data * 100) + '%', //这里我自动计算了，您可以直接给任意字符串
                        color: data.series[0].color,
                        fontSize: 25 * that.pixelRatio
                    },
                    subtitle: {
                        name: data.series[0].name, //这里您可以直接给任意字符串
                        color: '#666666',
                        fontSize: 12 * that.pixelRatio
                    },
                    extra: {
                        arcbar: {
                            type: 'circle', //整圆类型进度条图
                            width: that.arcbarWidth * that.pixelRatio, //圆弧的宽度
                            startAngle: 0.5 //整圆类型只需配置起始角度即可
                        }
                    }
                });
            },
            onBorrowing() {
                var that = this;
                busService.canBorrow({ userId: that.userId, token: util.getToken() });
            }
        },
        onLoad() {
            var that = this;
            appService.notice({}, function (obj, msg, code) {
                obj = obj['list'] || [that.$t('common.nonotice')];
                that.notice = obj[0]['value'];
            })
        },
        onShow: function () {
            var that = this;
            that.pageView({ callback: that.onInit });
        }
    }
</script>

<style lang="scss">
    .d-flex {
        display: flex;
    }
    .home {
        text-align: center;
        position: relative;
        padding-bottom: 15px;
        margin-right: -2px;
        margin-left: -2px;
        .icon-help {
            position: absolute;
            right: 20px;
            top: 14px;
            width: 1.25rem;
            img {
                width: 100%;
                height: auto;
            }
        }
        h1 {
            color: #fff;
            font-weight: normal;
            font-size: 1rem;
            position: absolute;
            top: 14px;
            left: 0;
            right: 0;
            width: 100%;
        }
        .tools {
            span {
                color: #fff;
                font-size: 1.25rem;
                span {
                    font-size: 0.875rem;
                }
            }
            button {
                margin-top: 1rem;
                background-color: #fff;
                color: #FF9700;
                width: 36px;
                height: 36px;
                border-radius: 50%;
                line-height: 36px;
                font-size: 22px;
                padding: 0;
                &.button-hover {
                    background-color: #ddd;
                }
                &[disabled] {
                    color: #fff;
                    background-color: #a5a5a5;
                }
            }
        }
        .bottom {
            position: absolute;
            bottom: 15px;
            left: 15px;
            right: 15px;
        }
    }

    .apply {
        display: block;
        width: 380upx;
        padding: 5px;
        margin-top: 1rem;
        font-size: 1rem;
        border-radius: 50px;
        background-color: #FF9700;
    }
</style>
