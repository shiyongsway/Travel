<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl"/>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "Recommend",
    data() {
      return {
        recommendList: [
          {
            id: '0001',
            imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg',
            title: '你好啊',
            desc: '海底世界',
          },
          {
            id: '0002',
            imgUrl: 'http://img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_200x200_c62292e9.jpg',
            title: '大熊猫',
            desc: '真的很可爱的大熊猫',
          },
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend-title
    line-height: 0.4rem
    background: #eee
    text-indent: 0.2rem

  .item
    display: flex
    overflow: hidden
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: 0.1rem
    .item-info
      flex: 1
      padding: 0.1rem
      min-width: 0
      .item-title
        line-height: 0.54rem
        font-size: 0.32rem
        color: #000000
        text-align: left
        ellipsis()
      .item-desc
        line-height: 0.54rem
        color: #ccc
        text-align: left
        ellipsis()
      .item-button
        line-height: 0.44rem
        background: #ff9300
        padding: 0.2rem 0.2rem
        border-radius: 0.03rem
        text-align: left
        float: left
        box-sizing: border-box;
</style>
