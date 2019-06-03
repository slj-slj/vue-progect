<template>
    <ul class="list">
        <li class="item" v-for="(item,key) of cities" :key="key">{{key}}</li>
    </ul>
</template>
<script>
export default {
    name:'CityAlphabet',
    props:{
        cities:Object
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .list
        position absolute
        top 1.72rem
        right 0
        bottom 0
        width .4rem
        display flex
        flex-direction column
        justify-content center
        .item
            line-height 0.38rem
            color $bgColor
            text-align center
</style>

