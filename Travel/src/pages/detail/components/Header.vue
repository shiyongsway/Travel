<template>
    <div>
      <router-link to='/'>
      <div class="header-abs" v-show="showAbs">
        <div class="iconfont header-abs-back">&#xe624;</div>
      </div>
      </router-link>

      <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">

        <router-link to="/">
          <div class="iconfont header-fixed-back">&#xe624;</div>
        </router-link>
        景点详情
      </div>

      </div>


</template>

<script>
    export default {
        name: "Header",
      data(){
          return{
            showAbs:true,
            opacityStyle:{
              opacity:0
            }
          }
      },
      activated(){
          console.log('activated')
          window.addEventListener('scroll',this.handleScroll)
      },
      deactivated(){
        window.removeEventListener('scroll',this.handleScroll)
      },

      methods:{
        handleScroll(){
          console.log('scroll')
          const top =document.documentElement.scrollTop
          if(top>104)
          {
            let opacity=top/204 - 0.50
            opacity = opacity>1 ? 1:opacity
            this.opacityStyle={
              opacity:opacity
            }
            this.showAbs=false

          }else {
            this.showAbs=true
          }

        },
      },


    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
  .header-abs
    z-index :2
    position: absolute
    left:0.2rem
    top: 1.3rem
    width: 0.8rem
    height: 0.8rem
    border-radius :0.4rem
    text-align :center
    line-height :0.8rem
    background :rgba(0,0,0,0.8)
    .header-abs-back
      color :#ffffff
  .header-fixed
    z-index: 2
    position: fixed
    top: 0rem
    left: 0
    right: 0
    height: 1.0rem
    line-height: 1.0rem
    text-align: center
    color: #fff
    background: #25a4bb
    font-size: .32rem
    .header-fixed-back
      position: absolute
      top: 0
      left: 0
      width: .64rem
      text-align: center
      font-size: .4rem
      color: #fff
</style>
