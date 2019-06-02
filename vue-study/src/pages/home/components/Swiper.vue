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
    data:function(){
        return {
            swiperOption:{
                pagination:'.swiper-pagination',
                loop:true
            },
            swiperList:[{
                id:'0001',
                imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/87a224d0349d94a11e97f31aa1aba4f5.jpg_750x200_1f78af87.jpg'
            },{
                id:'0002',
                imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/d7bbc21db442366a882e04ddc984669a.jpg_750x200_85e640d9.jpg'
            },{
                id:'0003',
                imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/667757f979fa38b12c4986f9930b6695.jpg_750x200_6cca7add.jpg'
            }]
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
    padding-bottom:26.67%
    background-color #ccc
    .swiper-img
      width:100%;
</style>
