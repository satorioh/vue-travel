<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handlerCityClick(item.name)">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配项</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handlerCityClick (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach(item => {
            if (item.spell.indexOf(this.keyword) > -1 || item.name.indexOf(this.keyword) > -1) {
              result.push(item)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
.search
  line-height : .72rem
  padding: 0 .1rem
  background : $bgColor
  .search-input
    box-sizing : border-box
    line-height : .62rem
    width : 100%
    text-align : center
    border-radius : .06rem
    color: #666
    padding: 0 .1rem
.search-content
  z-index: 1
  overflow : hidden
  position : absolute
  top: 1.58rem
  bottom: 0
  left: 0
  right: 0
  background : #eee
  .search-item
    line-height : .62rem
    padding-left : .2rem
    color: #666
    background : #fff
</style>
