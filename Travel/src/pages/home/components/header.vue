<template>
<div class="header">
  <div class="header-left">
    <span class="iconfont">&#xe624;</span>
  </div>
  <div class="header-input">
    <span class="iconfont">&#xe632;</span>
    输入城市</div>
  <div class="header-right">城市
    <span class="iconfont">&#xe64a;</span>
  </div>
</div>
</template>

<script>

    export default {
        name: "HomeHeader"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
  .header
    display:flex
    line-height:0.86rem
    background :$bgColor
    color :#fff
    .header-left
      width:0.64rem
      float:left
    .header-input
      flex 1
      height:0.64rem
      line-height:0.64rem
      background:#fff
      border-radius :0.1rem
      margin-top:0.12rem
      margin-left :.2rem
      color:#ccc
      text-align :left
    .header-right
      width :1.24rem
      float :right
      text-align center

</style>
