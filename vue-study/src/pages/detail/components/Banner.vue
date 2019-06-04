<template>
<div>
    <div class="banner" @click="handleBannerClick">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1409/05/dce6461a918adf226afd9f3119eb6b14.jpg_600x330_cee9b165.jpg">   
        <div class="banner-info">
            <div class="banner-title">大连圣亚海洋世界（AAAA景区）</div>
            <div class="banner-num"><span class="iconfont banner-icon">&#xe70b;</span>10</div>    
        </div> 
    </div> 
    <common-gallary :imgs="imgs" v-show="showGallary" @close="Close"></common-gallary>
</div>
    
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
    name:'DetailBanner',
    components: {
        CommonGallary
    },
    data(){
        return{
            showGallary :false,
            imgs :['http://img1.qunarzz.com/sight/p0/1507/64/897fcac6d5917229d9b7fc268666f381.water.jpg_r_800x800_cfb2955e.jpg'
                ,'http://img1.qunarzz.com/sight/p0/1507/64/897fcac6d5917229d9b7fc268666f381.water.jpg_r_800x800_cfb2955e.jpg']
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


