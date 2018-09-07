<template>
  <div>
    <Banner :bannerImg="bannerImg" :imgs="imgs"></Banner>
    <Header></Header>
    <DetailList :list="list"></DetailList>
  </div>
</template>

<script>
  import Banner from './components/Banner'
  import Header from './components/Header'
  import DetailList from './components/List'

  import axios from 'axios'

  export default {
        name: "Detail",
      components:{
        Banner,
        Header,
        DetailList
      },
    data(){
      return{
        bannerImg:''
        ,
        imgs:[],
        list:[]
        // list:[{
        //   title:'成人票',
        //     children:[{
        //       title:'成人三馆联票'
        //     },{
        //     title:'成人五馆联票'
        //   }]
        // },{
        //   title:'学生票'
        // },
        //   {
        //     title:'儿童票'
        //   },
        //   {
        //     title:'特惠票'
        //   },
      }
    },
    methods:{
      getDetailInfo(){
        axios.get('/api/detail.json?',{
          params:{
            id:this.$route.params.id
          }
        })
          .then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc(res){
        console.log(res.data.data)
        res=res.data
        if(res.ret && res.data){
          const data = res.data
          this.bannerImg=data.bannerImg
          this.imgs = data.gallaryImgs
          this.list = data.categoryList
        }
      }
    },
    mounted(){
      this.getDetailInfo()

    }
    }
</script>

<style lang="stylus" scoped>
</style>
