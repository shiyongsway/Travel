<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wraper">
            <div class="button">北京</div>
          </div>
          <div class="button-wraper">
            <div class="button">北京</div>
          </div>
          <div class="button-wraper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>

      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wraper" v-for="item of hotCities" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>

      <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for="innerItem of item" :key="innerItem.id "  @touchmove="handleTouchMove">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Bscroll from 'better-scroll'

  export default {
    name: "List",
    methods:{
      handleTouchMove(){
        console.log(1111)
      }
    },
    props:{
      hotCities:Array,
      cities:Object,
      letter:String
    },
    mounted() {
      this.scroll = new Bscroll(this.$refs.wrapper)
    },
    watch:{
      letter (){
        if(this.letter)
        {
          const element = this.$refs[this.letter][0]
          this.scroll.scrollToElement(element)

        }
      }
    }
  }

</script>

<style lang="stylus" scoped>
  .list
    position: absolute
    overflow: hidden
    top: 3rem
    left: 0
    right: 0
    bottom: 0
    .title
      line-height: 0.4rem
      background-color: #eee
      padding-left: 0.2rem
      color: #666
    .border-topbottom
      &:before
        border-color: #ccc
      &:after
        border-color: #ccc
    .button-list
      padding: 0.1rem 0.6rem 0.1rem 0.1rem
      overflow: hidden
      .button-wraper
        float: left
        width: 33.33%
        .button
          margin: 0.1rem
          text-align: center
          border: 0.02rem solid #ccc
    .item-list
      .item
        line-height: 0.54rem
        color: #666
        padding-left: 0.2rem
        text-align: left
      .border-bottom
        &:before
          border-color: red
</style>
