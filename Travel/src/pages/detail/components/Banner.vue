<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img"
           :src="this.bannerImg">
      <div class="banner-info">
        <div class="banner-title">产品编号433965</div>
        <div class="banner-icon"><span class="iconfont">&#xe632;</span>39</div>
      </div>
    </div>
    <FadeAnimation>
      <gallery :imgs="imgs" v-show="showgallery" @clickI="handleGalleryClick"></gallery>
    </FadeAnimation>
  </div>
</template>

<script>
  import Gallery from 'common/gallery/Gallery'
  import FadeAnimation from 'common/fade/fade'
  export default {
    props:{
      bannerImg:String,
      imgs:Array
    },
    name: "Banner",
    components: {
      Gallery,
      FadeAnimation,
    },
    data() {
      return {
        showgallery: false
      }

    },
    methods: {
      handleBannerClick() {
        this.showgallery = true;
      },
      handleGalleryClick() {
        this.showgallery = false
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 45%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      right: 0
      left: 0
      bottom: 0
      top: auto
      line-height: 0.6rem
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex: 1
        text-align: left
        color: #ffffff
        padding: 0 0.2rem
      .banner-icon
        color: #ffffffs
        padding: 0 0.2rem
        height: 0.4rem
</style>
