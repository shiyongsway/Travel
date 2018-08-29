<template>
  <div>
    <HomeHeader></HomeHeader>
    <my-swiper></my-swiper>
    <Icons></Icons>
  </div>
</template>
<script>
  import HomeHeader from './components/header'
  import MySwiper from './components/Swiper'
  import Icons from './components/Icons'
  export default {
      name:'Home',
    components:{
      HomeHeader,
      MySwiper,
      Icons,
    },
      methods:{

      }
    }
</script>
<style scoped>

</style>
