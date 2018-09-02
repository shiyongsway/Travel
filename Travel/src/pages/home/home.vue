<template>
  <div>
    <HomeHeader :city="city"></HomeHeader>
    <my-swiper :swiperList="swiperList"></my-swiper>
    <Icons :iconList="iconList"></Icons>
    <Recommend :recommendList2="recommendList2"></Recommend>
    <HomeWeekend :weekendList="weekendList"></HomeWeekend>
  </div>
</template>
<script>
  import HomeHeader from './components/header'
  import MySwiper from './components/Swiper'
  import Icons from './components/Icons'
  import Recommend from './components/Recommend'
  import HomeWeekend from './components/Weekend'
  import axios from 'axios'

  export default {
      name:'Home',
    components:{
      HomeHeader,
      MySwiper,
      Icons,
      Recommend,
      HomeWeekend,
    },
    data(){
      return {
        city:'',
        swiperList:[],
        iconList:[],
        recommendList2:[],
        weekendList:[],

      }
    },
      methods:{
        getHomeInfo(){
          axios.get('/api/index.json')
            .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc(res){
          console.log(res)
          res=res.data;
          if(res.ret && res.data){
            this.city = res.data.city
            this.swiperList= res.data.swiperList
            this.iconList=res.data.iconList
            this.recommendList2 = res.data.recommendList
            this.weekendList = res.data.weekendList
          }

        },
      },
    mounted(){
      this.getHomeInfo()
    },
    }
</script>
<style scoped>

</style>
