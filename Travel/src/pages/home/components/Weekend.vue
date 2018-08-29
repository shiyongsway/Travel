<template>
  <div>
    <div class="recommend-title">周末去哪</div>
    <ul>
      <li class="item" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl"/>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "HomeWeekend",
    data() {
      return {
        recommendList: [
          {
            id: '0001',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg',
            title: '灯',
            desc: '三个灯',
          },
          {
            id: '0002',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
            title: 'UFO',
            desc: '我要成功',
          },
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend-title
    line-height: 0.8rem
    background: #eee
    text-indent: 0.2rem
  .item-img-wrapper
    overflow :hidden
    height:0
    padding-bottom :37.66%
    .item-img
      width: 100%
  .item-info
    padding: 0.1rem
    .item-title
      line-height: 0.54rem
      font-size: 0.32rem
      text-align: left
      ellipsis()
    .item-desc
      line-height: 0.54rem
      color: #ccc
      text-align: left
      ellipsis()

</style>
