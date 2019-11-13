<script>
    export default {
        onLaunch: function() {
            console.log('App Launch');
            // #ifdef APP-PLUS
            // 锁定屏幕方向
            plus.screen.lockOrientation('portrait-primary'); //锁定
            // 检测升级
            uni.request({
                url: 'https://uniapp.dcloud.io/update', //检查更新的服务器地址
                data: {
                    appid: plus.runtime.appid,
                    version: plus.runtime.version,
                    imei: plus.device.imei
                },
                success: (res) => {
                    console.log('success', res);
                    if (res.statusCode == 200 && res.data.isUpdate) {
                        let openUrl = plus.os.name === 'iOS' ? res.data.iOS : res.data.Android;
                        // 提醒用户更新
                        uni.showModal({
                            title: '更新提示',
                            content: res.data.note ? res.data.note : '是否选择更新',
                            success: (showResult) => {
                                if (showResult.confirm) {
                                    plus.runtime.openURL(openUrl);
                                }
                            }
                        })
                    }
                }
            })

            var domModule = weex.requireModule('dom');
            domModule.addRule('fontFace', {
                'fontFamily': "uniicons",
                'src': "url('./static/uni.ttf')"
            });
            // #endif
        },
        onShow: function() {
            console.log('App Show')
        },
        onHide: function() {
            console.log('App Hide')
        },
		globalData: {
			test: ''
		}
    }
</script>

<style>
    /* #ifndef APP-PLUS-NVUE */
    /* uni.css - 通用组件、模板样式库，可以当作一套ui库应用 */
    @import './common/uni.css';

    /*每个页面公共css */
    *{
        margin:0;
        padding:0;
        list-style: none;
    }

    .content-body {
        width: 100vw;
        min-height: 100vh;
        background: #fff6db;
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;
    }
    .wave {
        position: relative;
        overflow: hidden;
    }
    .wave:after {
        content: "";
        display: block;
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        pointer-events: none;
        background-image: radial-gradient(circle, #666 10%, transparent 10.01%);
        background-repeat: no-repeat;
        background-position: 50%;
        transform: scale(10, 10);
        opacity: 0;
        transition: transform .3s, opacity .5s;
    }
    .wave:active:after {
        transform: scale(0, 0);
        opacity: .3;
        transition: 0s;
    }
    .wave:active {
        opacity: .8;
    }


    .logo_bottom {
        position: fixed;
        bottom: 0;
        width: 100%;
        height: 350rpx;
    }

    /*模态框弹出窗口的动画*/
    @keyframes moveUpAnimate {
        0% {
            transform: translateY(100%);
        }
        100% {
            transform: translateY(0);
        }
    }
    .moveUpAnimate {
        animation: moveUpAnimate .5s;
    }
    @keyframes fadeInAnimate {
        0% {
            opacity: 0;
        }
        100% {
            opacity: 1;
        }
    }
    .fadeInAnimate {
        animation: fadeInAnimate 0.5s;
    }
</style>
