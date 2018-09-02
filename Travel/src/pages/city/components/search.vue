<template>
  <div class="search">
    <input type="text" class="searchinput" placeholder="输入城市或拼音"/>
  </div>
</template>

<script>
    export default {
        name: "search"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
  .search
    height: 0.72rem
    padding:0.1rem
    background :$bgColor
    .searchinput
      height: 0.62rem
      line-height :.62rem
      width:100%
      padding :0.1rem
      box-sizing: border-box
</style>
