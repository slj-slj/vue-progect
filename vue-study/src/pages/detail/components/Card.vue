<template>
  <div class="card">
    <div class="card-desc border-bottom">
      <div class="card-left card-item">
        <h3>
          4.7分<span>超赞</span>
        </h3>
        <p>
          <span>1855条评论</span>
          <span>5条攻略</span>
        </p>
        <div class="iconfont card-icon">&#xe644;</div>
      </div>
      <div class="card-right card-item">
        <h4>景点简介</h4>
        <p>开放时间、贴士</p>
        <div class="iconfont card-icon">&#xe644;</div>
      </div>
    </div>
    <p class="card-address ">
        辽宁省大连市圣亚
        <span class="iconfont card-icon">&#xe644;</span>
    </p>
  </div>
</template>

<script>
  export default {
    name:'DetailCard',
  }
</script>

<style lang='stylus' scoped>
  @import '~@/assets/style/varibles.styl'
  .border-bottom
    &::before
      border-color #ccc
  .card
    padding .2rem .2rem 0
    border-bottom .2rem solid #f5f5f5
    .card-desc
      display flex
      .card-item
        position relative
        width 50%
        h3
          color #ff8300
          line-height .4rem
          font-size .32rem
          span
            font-size .28rem
            margin-left .1rem
        p
          color #9e9e9e
          font-size .24rem
          line-height .5rem
          span
            margin-right .1rem
        .card-icon
            position absolute
            right .2rem
            bottom 0
            top 0
            width .3rem
            height .3rem
            line-height .3rem
            margin auto
            font-size .32rem
            color #999
    .card-address
        position relative
        line-height .8rem
        .card-icon
            position absolute
            right .2rem
            bottom 0
            top 0
            width .3rem
            height .3rem
            line-height .3rem
            margin auto
            font-size .32rem
            color #999

</style>
