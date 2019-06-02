<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe7c2;</div>
        </div>
        <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题</div>
        <div class="header-right">{{this.city}}<span class="iconfont arrow-icon">&#xe62b;</span></div>
    </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props:{
    city:String
  }
}
</script>
<style lang="stylus" scoped>
  @import '~@/assets/style/varibles.styl'
  .header
    background-color:$bgColor;
    display :flex
    line-height: .86rem
    color:#fff
    .header-left
      width:.64rem
      float:left
      .back-icon
        text-align:center
        font-size:.4rem
    .header-input
      flex:1
      height:.64rem
      margin-top:.12rem
      margin-left:0.2rem
      background-color #fff
      border-radius:.08rem
      color:#ccc
      line-height:.64rem
      padding-left:.1rem
      overflow hidden
    .header-right
      width: 1.24rem
      text-align:center
      .arrow-icon
        margin-left:-.02rem
        font-size:.24rem
</style>
