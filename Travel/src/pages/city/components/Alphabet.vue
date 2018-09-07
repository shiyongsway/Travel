<template xmlns:v-touch="http://www.w3.org/1999/xhtml">
  <ul class="list">
    <li class="item" v-for="item of letters" :key="item" :ref="item" @click="handleLetterClick"
        @touchstart.prevent="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
    >{{item}}</li>
  </ul>
</template>

<script>
    export default {
        name: "Alphabet",
      props:{
        cities:Object,
      },
      data(){
          return{
            touchStatus:false,
            startY:0,
            timer:null
          }
      },
      updated(){
        this.startY=this.$refs['A'][0].offsetTop//A元素距离顶部的高度
      },
      methods:{
        handleLetterClick(e){
          this.$emit('change',e.target.innerText)
        },
        handleTouchStart(){
            this.touchStatus=true
            console.log('Start')
        },
        handleTouchMove(e){
          if(this.touchStatus){
            if(this.timer)
            {
              clearTimeout(this.timer)
            }
            this.timer=setTimeout(()=>{
              const touchY=e.touches[0].clientY -90
              const index = Math.floor( (touchY - this.startY)/20)-3
              console.log(index)
              this.$emit('change',this.letters[index])
            },16)

          }
        },
        handleTouchEnd(){
          this.touchStatus=false
          console.log('End')

        },
      },
      computed:{
           letters(){
             const letters =[]
             for(let item in this.cities){
               letters.push(item)
             }
             return letters
           }
      },
    }
</script>

<style lang="stylus" scoped>
  .list
    display: flex
    flex-direction :column
    justify-content :center
    position :absolute
    top:3rem
    right:0
    bottom:0
    width:0.4rem
    .item
      text-align: center
      line-height:0.4rem
      color: blue
</style>
