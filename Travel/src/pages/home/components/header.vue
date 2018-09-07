<template>
<div class="header">
  <div class="header-left">
    <span class="iconfont">&#xe624;</span>
  </div>
  <div class="header-input">
    <span class="iconfont">&#xe632;</span>
    输入城市</div>
  <router-link to='/city'>
    <div class="header-right">{{this.currentCity}}
      <span class="iconfont">&#xe64a;</span>
    </div>
  </router-link>

</div>
</template>

<script>
import {mapState,mapMutations,mapGetters} from  'vuex'

    export default {
        name: "HomeHeader",
      props:{
          city:String
      },
      computed:{
        ...mapState({
          currentCity:'city'
        }), //...展开运算符，mapState把vuex里的数据映射到这个计算属性里，把city的共用数据，映射到city这个计算属性里
        ...mapGetters(['doubleCity'])
      },
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
      min-width :1.04rem
      padding: 0.1rem
      float :right
      text-align center
      color :#ffffff;
</style>
