<template>
  <div>
    <HomeHeader></HomeHeader>
    <my-swiper></my-swiper>
    <div>Test</div>
  </div>
</template>
<script>
  import HomeHeader from './components/header'
  import MySwiper from './components/Swiper'
  export default {
      name:'Home',
    components:{
      HomeHeader,
      MySwiper
    },
      methods:{

      }
    }
</script>
<style scoped>

</style>
