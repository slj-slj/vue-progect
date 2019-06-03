<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">北京</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper" v-for="item of hot" :key="item.id">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item,key) of cities" :key="key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-bottom" v-for="innerItem of item" :key="innerItem.id">{{innerItem.name}}</div>
                </div>
            </div>
        </div>
        
    </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
    name:'CityList',
    props:{
        cities:Object,
        hot:Array
    },
    mounted () {
        this.scroll = new Bscroll(this.$refs.wrapper)
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .list
        position absolute
        top 1.72rem
        left 0
        right 0
        bottom 0
        overflow hidden
        .border-topbottom
            &:before
                border-color #ccc
            &:after
                border-color #ccc
        .title
            line-height:.5rem
            color #666
            background #eee
            font-size:.26rem
            padding-left 0.1rem
        .button-list
            overflow hidden
            padding .1rem .6rem .1rem .1rem
            .button-wrapper
                width 33.33%
                float:left
                .button
                    padding .1rem 0
                    margin:.1rem
                    border .01rem solid $bgColor
                    border-radius .12rem
                    text-align center
        .item-list
            overflow hidden
            padding:.1rem .6rem 0rem .1rem
            .item
                padding .2rem 0
                color #666
</style>

