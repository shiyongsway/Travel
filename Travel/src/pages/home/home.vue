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
  import {mapState} from  'vuex'

  export default {
    name: 'Home',
    components: {
      HomeHeader,
      MySwiper,
      Icons,
      Recommend,
      HomeWeekend,
    },
    computed: {
      ...mapState({
        currentCity: 'city'
      })
    },
    data() {
      return {
        lastCity: '',
        city: '',
        swiperList: [],
        iconList: [],
        recommendList2: [],
        weekendList: [],

      }
    },
    methods: {
      getHomeInfo() {
        axios.get('/api/index.json?' + this.currentCity)
          .then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc(res) {
        res = res.data;
        if (res.ret && res.data) {
          this.city = res.data.city
          this.swiperList = res.data.swiperList
          this.iconList = res.data.iconList
          this.recommendList2 = res.data.recommendList
          this.weekendList = res.data.weekendList
        }
      },
    },
    mounted() {
      this.lastCity = this.city
      this.getHomeInfo()
    },
    activated() {  //当页面重新显示的时候，就会执行activated
      if (this.lastCity !== this.city) {
        this.lastCity = this.city
        this.getHomeInfo()
      }
      console.log('updated')
    },

    updated() {

    }
  }
</script>
<style scoped>

</style>
