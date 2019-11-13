<template>
    <div class="content-body">
        <div class="uni-padding-wrap box">
            <div class="page-section">
                <div class="page-section-spacing">
                    <swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
                            :duration="duration">
                        <swiper-item>
                            <image mode="widthFix" class="banner" src="../../../static/food/banner.jpg"></image>
                        </swiper-item>

                        <swiper-item>
                            <image mode="widthFix" class="banner" src="../../../static/food/banner1.jpg"></image>
                        </swiper-item>

                    </swiper>
                </div>
            </div>
        </div>
        <div class="searchBox">
            <input class="input" name="" placeholder="请输入您要搜索的美食"/>
            <icon type="search" size="20" class="btn"/>
        </div>
        <div class="four-choose">
            <div class="four-son wave">
                <image mode="widthFix" class="icon" src="../../../static/food/icon.jpg"></image>
                <div class="text-icon">最新推荐</div>
            </div>

            <div class="four-son wave">
                <image mode="widthFix" class="icon" src="../../../static/food/icon1.jpg"></image>
                <div class="text-icon">热门菜谱</div>
            </div>

            <div class="four-son wave">
                <image mode="widthFix" class="icon" src="../../../static/food/icon2.jpg"></image>
                <div class="text-icon">人气菜肴</div>
            </div>

            <div class="four-son wave">
                <image mode="widthFix" class="icon" src="../../../static/food/icon3.jpg"></image>
                <div class="text-icon">优惠券</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        // name: "index"
        data() {
            return {
                autoplay: true,
                interval: 2500,
                duration: 500,
                indicatorDots: true,
            }
        },
        methods: {}
    }
</script>

<style scoped>
    .box,.page-section,.page-section-spacing {
        width: 100%;
        height: 250px;
        /*background: red;*/
    }
    .swiper{
        width: 100%;
        height: 100%;
    }

    .banner {
        width: 100%;
        /*height: 300px;*/
    }

    .searchBox {
        width: 70%;
        /*height: 50px;*/
        padding-bottom: 3px;
        background: white;
        margin-top: 15px;
        display: flex;
        align-items: center;
    }

    .input {
        width: 70%;
        height: 30px;
        border:none;
        outline: none;
        padding-left: 8px;
        font-size: 15px;
    }
    .btn{
        margin-left: 10%;
    }
    .four-choose{
        width: 100%;
        background: rgba(250,250,250,1);
        padding-bottom: 7px;
        display: flex;
        align-items: center;
        margin-top: 20px;
    }
    .four-son{
        width: 25%;
        /*background: yellow;*/
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .icon{
        width: 60%;
    }
    .text-icon{
        width: 70%;
        color: #929292;
        font-size: 15px;
        text-align: center;
        line-height: 20px;
    }
</style>