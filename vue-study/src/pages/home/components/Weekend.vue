<template>
    <div>
        <div  class="recommend-title">周末去哪</div>
        <ul> 
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img :src="item.imgUrl" class="item-img">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.itemTitle}}</p>
                    <p class="item-desc">{{item.itemDesc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:'HomeWeekend',
    data(){
        return {
            recommendList:[{
                id:'1001',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1507/cd/f7d2751cb82027f7f477bd8d73122dbc.water.jpg_350x240_a60ef4e4.jpg',
                itemTitle:'沈阳方特欢乐世界',
                itemDesc:'5A级著名景区，位于吉林省吉林市'
            },{
                id:'1002',
                 imgUrl:'http://img1.qunarzz.com/sight/p0/1702/87/8780653a41166464a3.img.jpg_350x240_f7953119.jpg',
                itemTitle:'沈阳方特欢乐世界',
                itemDesc:'5A级著名景区，位于吉林省吉林市'
            },{
                id:'1003',
                imgUrl:'http://img1.qunarzz.com/sight/p0/201406/25/3cc9a304f26d96a64067926d93f76387.jpg_350x240_46128252.jpg',
                itemTitle:'沈阳方特欢乐世界',
                itemDesc:'5A级著名景区，位于吉林省吉林市'
            }]
        }
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/mixins.styl'
    .recommend-title
        line-height:.8rem
        background-color #eeeeee
        margin-top:.2rem
        text-indent .2rem
        font-size 110%
        color #333
    .item-img-wrapper
        overflow hidden
        height 0
        padding-bottom 50%
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
            
</style>

