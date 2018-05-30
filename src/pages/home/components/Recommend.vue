<template>
  <div class="recommend">
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom">
        <img class="item-img" src="http://img1.qunarzz.com/sight/p0/1603/85/85aa0c000578a01e90.water.jpg_200x200_0ccb4aa8.jpg" alt="">
        <div class="item-info">
          <p class="item-info-title">拙政园</p>
          <p class="item-info-desc">江南园林甲天下，苏州园林甲江南</p>
          <button>查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend'
}
</script>

<style lang="stylus" scoped>
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
      .item-info-title
        line-height : .54rem
        font-size : .32rem
</style>
