<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl"/>
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
    export default {
        name: "Icons",
      props:{
        iconList:Array
      },
        data(){
          return{
            list:[
              {
                id:'0001',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                desc:'热门景点'
              },
              {
                id:'0002',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
                desc:'滑雪景点'
              },
              {
                id:'0003',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
                desc:'故宫'
              },
              {
                id:'0004',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                desc:'热门景点'
              },
              {
                id:'0005',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
                desc:'滑雪景点'
              },
              {
                id:'0006',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
                desc:'故宫'
              },
              {
                id:'0007',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                desc:'热门景点'
              },
              {
                id:'0008',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
                desc:'滑雪景点'
              },
              {
                id:'0009',
                imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
                desc:'故宫'
              },
            ],
          }
        },
      computed:{
        pages() {
          const pages=[]
          this.iconList.forEach((item,index)=>{
            const page=Math.floor(index / 8)
            if(!pages[page]){
              pages[page]=[]
            }
            pages[page].push(item)
          })
          return pages
        }
      }
    }
</script>

<style lang="stylus" scoped>
@import "~@/assets/style/variables.styl"
@import "~@/assets/style/mixins.styl"
  .icons >>> .swiper-container
    height :0
    padding-bottom :50%
  .icon
    height:0
    position: relative
    width: 25%
    float: left
    padding-bottom:25%
    .icon-img
      position: absolute
      top:0
      left:0
      right: 0
      bottom :0.44rem
      /*background:blue*/
      box-sizing :border-box
      padding :0.1rem
      .icon-img-content
        height :100%
        display :block
        margin:0 auto
    .icon-desc
      position: absolute
      left :0
      right:0
      height: 0.44rem
      bottom:0
      line-height: 0.44rem
      color :$darkTextColor
      ellipsis()
</style>
