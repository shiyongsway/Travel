<template>
    <div class="header">
      <router-link to="/">
        <span class="iconfont headerBack">&#xe624;</span>
      </router-link>

      城市选择
    </div>
</template>

<script>
    export default {
        name: "cityHeader"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
  .header
    overflow:hidden
    height:0.86rem
    line-height:0.86rem
    text-align: center
    color :#fff
    background :$bgColor
    .headerBack
      float :left
      color:#ffffff
</style>
