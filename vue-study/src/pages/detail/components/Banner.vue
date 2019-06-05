<template>
<div>
    <div class="banner" @click="handleBannerClick">
        <img class="banner-img" :src="bannerImg">   
        <div class="banner-info">
            <div class="banner-title">{{this.sightName}}</div>
            <div class="banner-num"><span class="iconfont banner-icon">&#xe70b;</span>{{this.gallaryImgs.length}}</div>    
        </div> 
    </div> 
    <detail-animation>
        <common-gallary :gallaryImgs="gallaryImgs" v-show="showGallary" @close="Close"></common-gallary>
    </detail-animation>
</div>
    
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
import DetailAnimation from 'common/animation/animation'
export default {
    name:'DetailBanner',
    components: {
        CommonGallary,
        DetailAnimation
    },
    props:{
        sightName:String,
        bannerImg:String,
        gallaryImgs:Array
    },
    data(){
        return{
            showGallary :false
        }
    },
    methods: {
        handleBannerClick(){
            this.showGallary = true
        },
        Close(){
            this.showGallary = false
        }
    }
}
</script>
<style lang="stylus" scoped>
    .banner
        overflow hidden
        position relative
        height 0
        padding-bottom 55%
        .banner-img
            width 100%
        .banner-info
            position absolute
            left 0
            right 0
            bottom 0
            line-height .6rem
            display flex
            background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
            .banner-title
                flex 1
                color #fff
                font-size .32rem
                padding .1rem
            .banner-num
                padding 0 .4rem
                height .4rem
                line-height .4rem
                margin-top .2rem
                border-radius .2rem
                background-color rgba(0,0,0,0.6)
                color #fff
                font-size .24rem
                .banner-icon
                    font-size .24rem
</style>


