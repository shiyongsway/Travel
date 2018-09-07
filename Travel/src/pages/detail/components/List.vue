<template>
<div>
  <div class="item" v-for="(item,index) of list" :key="index">
    <div class="item-title border-bottom">
      <span class="item-title-icon"></span>
      {{item.title}}
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</div>
</template>

<script>
    export default {
        name: "DetailList",
        props:{
          list:Array
        }
    }
</script>

<style lang="stylus" scoped>
  .border-bottom
    &:before
      border-color: red
  .item-title
    line-height :0.8rem
    font-size :0.32rem
    padding :0.2rem
    text-align: left
    .item-title-icon
      position: relative
      left: .06rem
      top: .06rem
      width: .36rem
      height: .36rem
      display :inline-block
      background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
      margin-right: .1rem
      background-size: .4rem 3rem
  .item-children
    line-height:0.8rem
    font-size :0.32rem
    padding :0 0.2rem
</style>
