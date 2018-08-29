<template>
  <div>
    <HomeHeader></HomeHeader>
    <my-swiper></my-swiper>
    <Icons></Icons>
    <Recommend></Recommend>
    <HomeWeekend></HomeWeekend>
  </div>
</template>
<script>
  import HomeHeader from './components/header'
  import MySwiper from './components/Swiper'
  import Icons from './components/Icons'
  import Recommend from './components/Recommend'
  import HomeWeekend from './components/Weekend'

  export default {
      name:'Home',
    components:{
      HomeHeader,
      MySwiper,
      Icons,
      Recommend,
      HomeWeekend,
    },
      methods:{

      }
    }
</script>
<style scoped>

</style>
