<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl"></img>
      </swiper-slide>

      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div><!--显示页面图中的小点-->
    </swiper>
  </div>
</template>

<script>
  export default {
    name: "MySwiper",
    props:{
      swiperList:Array
    }
    ,
    data: function () {
      return {
        swiperOption: {
          pagination:{
            el:'.swiper-pagination',
          },
          loop:true,
        },
      }
    },
  }


</script>

<style lang="stylus" scoped>
  .wrapper >>>  .swiper-pagination-bullet-active
    background-color :#ffffff !important
  .wrapper
    overflow:hidden
    width :100%
    height :0
    padding-bottom :25.87%
    .swiper-paginatin-bullet-active
      background-color :red !important
    .swiper-img
      width:100%

</style>
