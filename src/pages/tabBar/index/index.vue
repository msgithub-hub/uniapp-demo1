<template>
    <div class="content-body">
        <div class="uni-padding-wrap box">
            <div class="page-section swiper">
                <div class="page-section-spacing">
                    <swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
                            :duration="duration">
                        <swiper-item>
                            <!--<view class="swiper-item uni-bg-red">A</view>-->
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
    .box {
        width: 100%;
        /*height: 700px;*/
    }

    .banner {
        width: 100%;
        height: 300px;
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
</style>