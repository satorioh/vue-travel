<template>
  <div>
    <div class="banner" @click="handlerBannerClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-info-title">{{sightName}}</div>
        <div class="banner-info-number"><span class="iconfont banner-icon">&#xe626;</span>{{gallaryImgs.length}}</div>
      </div>
    </div>
    <fade-animation>
      <common-gallery :imgs="gallaryImgs" v-show="galleryShow" @close="handlerGalleryClose"></common-gallery>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  components: {
    'common-gallery': CommonGallery,
    'fade-animation': FadeAnimation
  },
  data () {
    return {
      galleryShow: false
    }
  },
  methods: {
    handlerBannerClick () {
      this.galleryShow = true
    },
    handlerGalleryClose () {
      this.galleryShow = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position : relative
    overflow: hidden
    height : 0
    padding-bottom : 55%
    .banner-img
      width : 100%
    .banner-info
      display : flex
      position : absolute
      left: 0
      right: 0
      bottom: 0
      line-height : .6rem
      color: #fff
      background-image : linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.8))
      .banner-info-title
        flex: 1
        font-size : .32rem
        padding: 0 .2rem
      .banner-info-number
        margin-top : .14rem
        padding: 0 .4rem
        background : rgba(0,0,0,.8)
        border-radius : .2rem
        line-height : .32rem
        height: .32rem
        font-size: .24rem
        .banner-icon
          font-size : .24rem
</style>
