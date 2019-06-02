<template>
    <div class="search">
        <input type="text" placeholder="输入城市名或拼音" class="search-city">
    </div>
</template>
<script>
export default {
    name:'CitySearch'
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .search
        padding 0 .1rem
        height $headerHeight
        line-height $headerHeight
        background-color $bgColor
        text-align center
        .search-city
            color:#666
            width 96%
            height .62rem
            line-height .62rem
            padding:0 .1rem
            border-radius .06rem
            box-sizing border-box
</style>

