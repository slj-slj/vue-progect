<template>
    <div>
        <div class="header-abs" v-show="showAbs">
            <router-link tag="div" to="/" class="iconfont header-abs-icon">&#xe7c2;</router-link>
        </div>
        <div 
            class="header-fixed" 
            v-show="!showAbs"
            :style="opacityStyle"
        >
                景点详情
                <router-link to="/">
                    <div class="iconfont header-fixed-back">&#xe7c2;</div>
                </router-link>
        </div>
    </div>
</template>
<script>
export default {
    name:'DetailHeader',
    data(){
        return{
            showAbs:true,
            opacityStyle:{
                opacity:0
            }
        }
    },
    methods: {
        handleScroll(){
            const top = document.documentElement.scrollTop
            if(top > 60){
                let opacity =top / 140
                opacity = opacity >1 ? 1 : opacity
                this.opacityStyle = {
                    opacity
                }
                // opacity = opacity > 1 ? 1 :0
                this.showAbs = false
            }else{
                this.showAbs = true
            }
        }
    },
    activated () {
        window.addEventListener('scroll',this.handleScroll)
    },
    deactivated () {
        window.removeEventListener('scroll',this.handleScroll)
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .header-abs
        position absolute
        left .2rem
        top .2rem
        width .8rem
        height .8rem 
        border-radius .4rem
        text-aline center
        line-height .8rem
        background-color rgba(0,0,0,0.5)
        .header-abs-icon
            color #ffffff
            font-size .4rem
            text-align center
    .header-fixed
        position fixed
        z-index 2
        top 0
        left 0
        right 0
        height $headerHeight
        line-height $headerHeight
        background-color $bgColor
        text-align center
        color #fff
        font-size 130%
        .header-fixed-back
            position absolute 
            top 0
            left 0
            width .64rem
            text-align center
            font-size:120%
            color #fff

</style>


