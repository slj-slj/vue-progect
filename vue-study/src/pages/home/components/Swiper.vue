<template>
<div class="wrapper">
    <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="item of swiperList" :key="item.id"><img class="swiper-img" :src="item.imgUrl"/></swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
</div>
</template>
<script>
export default {
  name:'HomeSwiper',
  props:{
      swiperList:Array
  },
  data:function(){
    return {
        swiperOption:{
            pagination:'.swiper-pagination',
            loop:true,
            autoplay:3000
        }
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
      background-color #fff
  .wrapper
    width:100%
    height:0
    overflow hidden
    padding-bottom:31.25%
    background-color #ccc
    .swiper-img
      width:100%;
</style>
