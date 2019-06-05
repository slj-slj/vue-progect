<template>
    <div>
        <div class="item" v-for="(item,index) of list" :key="index">
            <div class="item-title border-bottom">
                <span class="item-title-icon"></span>
                {{item.title}}
            </div>
            <div class="recommend-info border-bottom">
                <div class="recommend-left">
                    <h4 class="recommend-title">【官方直销  随时入园】大连圣亚海洋世界四馆{{item.title}}票</h4>
                    <p>16:00前随买随用</p>
                    <span class='border'>随时退</span>
                </div>
                <div class="recommend-right">
                    <span>{{item.money}}</span>
                    <div class='recommend-button'>预定</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'DetailList',
    props:{
        list:Array
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .item 
        padding-left .2rem
        .item-title
            line-height .8rem
            font-size .32rem
            .item-title-icon
                position relative
                left .03rem
                top .06rem
                display: inline-block;
                width: .36rem;
                height: .36rem;
                background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
                background-size: .4rem 3rem;
        .recommend-info
            display:flex
            justify-content:space-between
            padding:.2rem 0
            .recommend-left
            width:5.72rem
            color:#616161
            h4
                display: -webkit-box
                overflow:hidden
                line-height:.6rem
                font-size:.4rem
                -webkit-line-clamp: 2
                -webkit-box-orient: vertical
            p
                line-height:.5rem
                font-size:.28rem
            span
                color:#00afc7
                font-size:.24rem
            .recommend-right
                display:flex
                flex-direction:column
                justify-content:center
                width:1.8rem
                padding-right .2rem
                text-align:center
                span
                    color:#ff9852
                    font-size:.35rem
                    font-weight:400
                .recommend-button
                    height:.6rem
                    color:#fff
                    background-image: linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%)
                    line-height:.6rem
                    border-radius:.1rem
</style>


