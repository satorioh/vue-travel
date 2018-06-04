<template>
  <div class="recommend">
    <div class="title">热销推荐</div>
    <ul>
        <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item of list" :key="item.id">
          <img class="item-img" :src="item.imgUrl" alt="">
          <div class="item-info">
            <p class="item-info-title">{{item.title}}</p>
            <p class="item-info-desc">{{item.desc}}</p>
            <button class="item-info-button">查看详情</button>
          </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
  // data () {
  //   return {
  //     recommendList: [
  //       {
  //         id: '01',
  //         imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/85/85aa0c000578a01e90.water.jpg_200x200_0ccb4aa8.jpg',
  //         title: '拙政园',
  //         desc: '江南园林甲天下，苏州园林甲江南'
  //       },
  //       {
  //         id: '02',
  //         imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/6f/6fd1ba315b60e430a3.water.jpg_200x200_16184926.jpg',
  //         title: '周庄',
  //         desc: '江南园林甲天下，苏州园林甲江南'
  //       },
  //       {
  //         id: '03',
  //         imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/14/3dfad2bcd30c40e91a15f8b7296d86a6.jpg_200x200_265db173.jpg',
  //         title: '同里古镇',
  //         desc: '江南园林甲天下，苏州园林甲江南'
  //       },
  //       {
  //         id: '04',
  //         imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/27/6640b07ce9a3dd7d9e37743ff58c1c3f.water.jpg_200x200_d7cd9982.jpg',
  //         title: '木渎古镇',
  //         desc: '江南园林甲天下，苏州园林甲江南'
  //       }
  //     ]
  //   }
  // }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .title
    line-height : .8rem
    background : #eee
    text-indent : .2rem
  .item
    display : flex
    overflow : hidden
    height : 1.9rem
    .item-img
      width : 1.7rem
      height : 1.7rem
      padding: .1rem
    .item-info
      flex : 1
      padding: .1rem
      min-width : 0
      .item-info-title
        line-height : .54rem
        font-size : .32rem
        ellipsis()
      .item-info-desc
        line-height : .4rem
        color: #ccc
        ellipsis()
      .item-info-button
        line-height : .44rem
        margin-top : .16rem
        background : #ff9300
        padding: 0 .2rem
        border-radius : .06rem
        color: #fff
</style>
