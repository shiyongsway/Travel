<template>
  <div class="container" @click="handleGalleryClick">
    <div class="wrapper">


    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="(item,index) of imgs" :key="index">
        <img class="swiper-img"  :src="item"></img>
      </swiper-slide>

      <!--&lt;!&ndash; Optional controls &ndash;&gt;-->
      <div class="swiper-pagination" slot="pagination"></div><!--显示页面图中的小点-->
    </swiper>

    </div>
  </div>
</template>

<script>
   export default {
        name: "Gallery",
     props:{
        imgs:{
          type:Array,
          default(){
            return[]
          }
        }
     },
      data: function () {
        return {
          swiperOption: {
            pagination:{
              el:'.swiper-pagination',
              type : 'fraction',
            },
            loop:true,
            observeParents: true, //只要监听我这个元素或父级元素发生了变化，会进行自动刷新一次，就可以解决Swiper宽度计算的问题
            observer: true
          },
        }
      },
     methods:{
       handleGalleryClick(){
         this.$emit('clickI')
       }
     }


    }
</script>

<style  lang="stylus" scoped>
  .container
    z-index:3
    display :flex
    flex-direction :column
    justify-content :center
    position :fixed
    left:0
    right:0
    top:0
    bottom:0
    background :#000
    .wrapper
      overflow :hidden
      height:0
      width:100%
      padding-bottom :100%
      .swiper-img
        width:100%
      .swiper-pagination
        color :#ffffff
        bottom:0rem
</style>
