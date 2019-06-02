<template>
    <div>
        <div  class="recommend-title">周末去哪</div>
        <ul> 
            <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img :src="item.imgUrl" class="item-img">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
        <div class="more">查看更多</div>
    </div>
</template>
<script>
export default {
    name:'HomeWeekend',
    props:{
        weekendList:Array
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/mixins.styl'
    .recommend-title
        line-height:.8rem
        background-color #eeeeee
        text-indent .2rem
        font-size 110%
        color #333
    .item-img-wrapper
        overflow hidden
        height 0
        padding-bottom 38%
    .item-img
        width 100%
    .item-info
        padding .1rem
        min-width 0
        .item-title
            line-height .54rem
            font-size .32rem
            ellipsis()
        .item-desc
            line-height:.44rem
            color:#ccc
            ellipsis()
    .more
        width:100%
        height .8rem
        line-height .8rem
        text-align center
        font-size:120%;
</style>

