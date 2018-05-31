<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-content">
            <img :src="item.imgUrl" alt="">
            <p class="icon-text">{{item.desc}}</p>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  // data () {
  //   return {
  //     iconList: [
  //       {
  //         id: '01',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
  //         desc: '景点门票门票门票'
  //       },
  //       {
  //         id: '02',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
  //         desc: '古镇'
  //       },
  //       {
  //         id: '03',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
  //         desc: '名胜古迹'
  //       },
  //       {
  //         id: '04',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
  //         desc: '游乐场'
  //       },
  //       {
  //         id: '05',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
  //         desc: '踏青赏花'
  //       },
  //       {
  //         id: '06',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
  //         desc: '一日游'
  //       },
  //       {
  //         id: '07',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png',
  //         desc: '苏州园林'
  //       },
  //       {
  //         id: '08',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
  //         desc: '拙政园'
  //       },
  //       {
  //         id: '09',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
  //         desc: '虎丘'
  //       },
  //       {
  //         id: '10',
  //         iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
  //         desc: '南浔古镇'
  //       }
  //     ]
  //   }
  // },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
  .icons
    overflow : hidden
    height : 0
    padding-bottom : 50%
    /*background : green*/
    .icon
      position : relative
      float : left
      width : 25%
      padding-bottom: 25%
      height : 0
      background : #fff
      .icon-content
        width : 100%
        position : absolute
        top: 50%
        transform : translateY(-50%)
        text-align : center
        img
          width : 1.1rem
          height : 1.1rem
        .icon-text
          font-size : .28rem
          color: $darkTextColor
          margin-top : .1rem
          ellipsis()
</style>
