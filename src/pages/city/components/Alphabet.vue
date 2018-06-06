<template>
  <ul class="list">
    <li class="item" v-for="item of letters" :key="item" :ref="item" @click="handlerClick" @touchstart.prevent="handlerTouchStart" @touchmove="handlerTouchMove" @touchend="handlerTouchEnd">{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handlerClick (e) {
      this.$emit('change', e.target.textContent)
    },
    handlerTouchStart () {
      this.touchStatus = true
    },
    handlerTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 78.4
          const index = Math.floor((touchY - this.startY) / 20)
          console.log(index)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handlerTouchEnd () {
      this.touchStatus = false
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display : flex
    flex-direction : column
    justify-content : center
    position : absolute
    top: 1.58rem
    bottom: 0
    right : 0
    width : .4rem
    .item
      line-height : .4rem
      color: $bgColor
      text-align : center
</style>
