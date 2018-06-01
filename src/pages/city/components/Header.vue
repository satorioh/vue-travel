<template>
  <div class="header">
    <router-link to="/">
      <span class="iconfont header-back-icon">&#xe624;</span>
    </router-link>
    <h1 class="header-title">城市选择</h1>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
.header
  position : relative
  overflow : hidden
  line-height : $headerHeight
  color: #fff
  text-align : center
  font-size : .32rem
  background : $bgColor
  .header-back-icon
    position : absolute
    left : 0
    width: .64rem
    color: #fff
</style>
