<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key="item.id" v-if="list.length"><img class="swiper-img" :src="item.imgUrl" alt=""></swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000
      }
      // swiperList: [
      //   {
      //     id: '0001',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/77/f63bd04dd5319602.jpg_750x200_6ba8e0ca.jpg'
      //   },
      //   {
      //     id: '0002',
      //     imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/e5/59fad13a64807d02.jpg_750x200_713ae984.jpg'
      //   }
      // ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
                 background : #fff
  .wrapper
    overflow : hidden
    width : 100%
    height : 0
    padding-bottom : 31.25%
    background : #eee
    .swiper-img
      width : 100%
</style>
