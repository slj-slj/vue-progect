<template>
    <div class="banner">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1409/05/dce6461a918adf226afd9f3119eb6b14.jpg_600x330_cee9b165.jpg">   
        <div class="banner-info">
            <router-link tag="div" to="/">
                <div class="iconfont banner-back">&#xe7c2;</div>
            </router-link>
            <div class="banner-title">大连圣亚海洋世界（AAAA景区）</div>
            <div class="banner-num"><span class="iconfont banner-icon">&#xe70b;</span>10</div>    
        </div> 
    </div> 
</template>
<script>
import DetailBanner from './components/Banner'
export default {
    name:'Detail',
    components: {
        DetailBanner
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
            top 0
            bottom 0
            line-height .6rem
            display flex
            background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
            .banner-back
                width .6rem
                height .6rem
                line-height .6rem
                margin-top .1rem
                background-color rgba(0,0,0,0.6)
                font-size .32rem
                position absolute
                top 0.2rem
                left 0.1rem
                border-radius .3rem
                text-align center
                color #fff
            .banner-title
                position absolute
                bottom 0
                left .05rem
                color #fff
                font-size .32rem
                padding .1rem
            .banner-num
                position absolute
                bottom 0.8rem
                left .1rem
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


