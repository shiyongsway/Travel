<template>
  <div>
    <div class="search">
      <input type="text" class="searchinput" v-model="keyword" placeholder="输入城市或拼音"/>
    </div>

    <div class="search-content" ref="wrapper" v-show="keyword">
      <div>
        <ul>
          <li v-for="item of list" :key="item.id" class="search-item border-bottom" @click="handleSearchClick(item.name)">{{item.name}}</li>
          <li  class="search-item border-bottom" v-show="hasNoData" >没有查询到数据</li>
        </ul>
      </div>
    </div>

  </div>

</template>

<script>
  import Bscroll from 'better-scroll'

  export default {
    name: "search",
    data() {
      return {
        keyword: '',
        list: [],
        timer: null
      }
    },
    props: {
      cities: Object
    },
    watch: {
      keyword() {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        if (!this.keyword) {
          this.list = []
          return
        }
        this.timer = setTimeout(() => {
          const result = []
          for (let i in this.cities) {
            this.cities[i].forEach((value) => {
              if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
                result.push(value)
              }
            })
          }
          this.list = result
        }, 100)
      },
    },

    mounted() {
      this.scroll = new Bscroll(this.$refs.wrapper)
    },

    computed:{
      hasNoData(){
        return !this.list.length
      }
    },
    methods:{
      handleSearchClick(city){
        this.$store.commit('changeCity',city)
        this.$router.push('/')

      }
    },






  }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
  .border-bottom
    &:before
      border-color: red

  .search
    position: relative
    height: 0.72rem
    padding: 0.1rem
    background: $bgColor
    .searchinput
      height: 0.62rem
      line-height: .62rem
      width: 100%
      padding: 0.1rem
      box-sizing: border-box

  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 3rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item
      line-height: 0.62rem
      padding-left: 0.2rem
      color: #666
</style>
