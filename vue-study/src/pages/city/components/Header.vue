<template>
    <div class="header">
        城市选择
        <router-link to="/">
            <div class="iconfont header-back">&#xe7c2;</div>
        </router-link>
        
    </div>
</template>
<script>
export default {
    name:'CityHeader'
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .header
        position relative
        height $headerHeight
        line-height $headerHeight
        background-color $bgColor
        text-align center
        color #fff
        font-size 130%
        .header-back
            position absolute 
            top 0
            left 0
            width .64rem
            text-align center
            font-size:120%
            color #fff
</style>

