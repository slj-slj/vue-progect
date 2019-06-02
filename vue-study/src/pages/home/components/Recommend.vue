<template>
    <div>
        <div  class="recommend-title">热销推荐</div>
        <ul> 
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img :src="item.imgUrl" class="item-img">
          
                <div class="item-info">
                    <p class="item-title">{{item.itemTitle}}</p>
                    <p class="item-desc">{{item.itemDesc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:'HomeRecommend',
    data(){
        return {
            recommendList:[{
                id:'1001',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1409/05/dce6461a918adf226afd9f3119eb6b14.jpg_350x240_d76e3122.jpg',
                itemTitle:'五虎岛',
                itemDesc:'5A级著名景区，位于吉林省吉林市'
            },{
                id:'1002',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1702/98/98a890af4b2d7d89a3.img.jpg_200x200_dfc9cbbb.jpg',
                itemTitle:'圣鑫世外桃源温泉谷',
                itemDesc:'5A级著名景区，位于吉林省吉林市'
            },{
                id:'1003',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1602/9f/9fc20948e19c112b90.img.jpg_200x200_14efa636.jpg',
                itemTitle:'吉林神农温泉度假村',
                itemDesc:'5A级著名景区，位于吉林省吉林市'
            },{
                id:'1004',
                imgUrl:'http://img1.qunarzz.com/sight/p65/201211/09/b7ac0fb597ff697a93835fbb.jpg_200x200_5f1b16a2.jpg',
                itemTitle:'拉法山',
                itemDesc:'5A级著名景区，位于吉林省吉林市'
            },{
                id:'1005',
                imgUrl:'http://img1.qunarzz.com/sight/p0/201406/25/222944c4d364b3d6e9064465071a898e.jpg_200x200_53fe0c3c.jpg',
                itemTitle:'五虎岛游乐园（水世界）',
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
    .item
        display flex
        height 1.9rem
        overflow hidden
        .item-img
            width 1.7rem
            height 1.7rem
            padding:.1rem
        .item-info
            flex 1
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
            .item-button
                line-height:.44rem
                background-color #ff9300
                padding 0 .2rem
                border-radius .06rem
                margin-top:.16rem
                color:#fff
                
</style>

