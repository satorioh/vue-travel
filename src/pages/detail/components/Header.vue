<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <span class="iconfont header-back-icon">&#xe624;</span>
      </router-link>景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handlerScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handlerScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
.header-abs
  position : absolute
  left: .2rem
  top: .2rem
  width : .8rem
  height : .8rem
  line-height : .8rem
  text-align : center
  border-radius : .4rem
  background : rgba(0, 0, 0, .8)
  .back-icon
    color: #fff
.header-fixed
  position : fixed
  top: 0
  left: 0
  right: 0
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
