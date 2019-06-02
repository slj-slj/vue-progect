<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img"><img :src="item.imgUrl" class="icon-imgcontent"></div>
                    <p class="icon-desc">{{item.font}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
export default {
  name:'HomeIcons',
  data:function(){
      
      return{
        swiperOption:{
            autoPlay:"false" 
        },
        List:[
          {
              id:'0001',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
              font:'景点门票'
          },
          {
              id:'0002',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
              font:'一日游'
          },
          {
              id:'0003',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
              font:'泡温泉'
          },
          {
              id:'0004',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/87/20656da0ac042002.png',
              font:'长白山'
          },
          {
              id:'0005',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
              font:'景点门票'
          },
          {
              id:'0006',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
              font:'一日游'
          },
          {
              id:'0007',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
              font:'泡温泉'
          },
          {
              id:'0008',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/87/20656da0ac042002.png',
              font:'长白山'
          },
          {
              id:'0009',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
              font:'景点门票'
          },
          {
              id:'0010',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
              font:'一日游'
          },
          {
              id:'0011',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
              font:'泡温泉'
          },
          {
              id:'0012',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/87/20656da0ac042002.png',
              font:'长白山'
          }
        ],
      }
      
  },
  computed:{
      pages(){
          const pages = []
          this.List.forEach((item,index)=>{
              const page = Math.floor(index/8)
              if(!pages[page]){
                  pages[page] = []
              }
              pages[page].push(item)
          })
          return pages
      }
  }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    @import '~@/assets/style/mixins.styl'
    .icons >>> .swiper-container
        height:0
        padding-bottom:50%
    .icon
        width:25%
        float:left
        padding-bottom:25%
        position: relative
        height:0
        .icon-img
            position:absolute
            top:0
            left:0
            right:0
            bottom:.44rem
            box-sizing:border-box
            padding:.1rem
            .icon-imgcontent
                display:block
                height:100%
                margin:0 auto
        .icon-desc
            position:absolute
            left:0
            right:0
            bottom:0
            height:.44rem
            line-height :.44rem
            color:$darkTextColor
            text-align:center
            ellipsis()

</style>
