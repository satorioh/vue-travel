<template>
  <div class="recommend">
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-info-title">{{item.title}}</p>
          <p class="item-info-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [
        {
          id: '01',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/8a/d412db9fcd44dd.jpg_r_640x214_86f303a2.jpg',
          title: '拙政园',
          desc: '江南园林甲天下，苏州园林甲江南'
        },
        {
          id: '02',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/70/b2f8425ce486ed.jpg_r_640x214_5db9de57.jpg',
          title: '周庄',
          desc: '江南园林甲天下，苏州园林甲江南'
        },
        {
          id: '03',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1507/ab/1c456b9cbffc31.jpg_r_640x214_1c2552de.jpg',
          title: '同里古镇',
          desc: '江南园林甲天下，苏州园林甲江南'
        },
        {
          id: '04',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/3e/18b666031b22e7.jpg_r_640x214_864dce2f.jpg',
          title: '木渎古镇',
          desc: '江南园林甲天下，苏州园林甲江南'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .title
    line-height : .8rem
    background : #eee
    text-indent : .2rem
  .item-img-wrapper
    overflow : hidden
    height : 0
    padding-bottom : 33.9%
    .item-img
      width : 100%
  .item-info
    padding: .2rem
    min-width : 0
    .item-info-title
      line-height : .54rem
      font-size : .32rem
      ellipsis()
    .item-info-desc
      line-height : .4rem
      color: #ccc
      ellipsis()
</style>
