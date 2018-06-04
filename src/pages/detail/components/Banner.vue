<template>
  <div>
    <div class="banner" @click="handlerBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1603/85/85aa0c000578a01e90.water.jpg_600x330_6dddcf68.jpg" alt="">
      <div class="banner-info">
        <div class="banner-info-title">拙政园(AAAAA景区)</div>
        <div class="banner-info-number"><span class="iconfont banner-icon">&#xe626;</span>39</div>
      </div>
    </div>
    <common-gallery :imgs="imgs" v-show="galleryShow" @close="handlerGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  components: {
    'common-gallery': CommonGallery
  },
  data () {
    return {
      imgs: ['http://img1.qunarzz.com/sight/p0/1707/a0/a03d76d7a3ceace9a3.img.png_r_800x800_4e424e00.png', 'http://img1.qunarzz.com/sight/p0/1707/69/6955be3eda826b3a3.img.png_r_800x800_8fdcde1d.png'],
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
