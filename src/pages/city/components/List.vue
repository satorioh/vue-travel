<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrap">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrap" v-for="item of hotCities" :key="item.id" @click="handlerCityClick(item.name)">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,index) of cities" :key="index" :ref="index">
        <div class="title border-topbottom">{{index}}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for="innerItem of item" :key="innerItem.id" @click="handlerCityClick(innerItem.name)">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState } from 'vuex'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  methods: {
    handlerCityClick (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color : #ccc
    &:after
      border-color : #ccc
  .border-bottom
  &:before
    border-color : #ccc
  .list
    overflow : hidden
    position : absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .title
      line-height : .54rem
      background : #eee
      padding-left : .2rem
      font-size : .26rem
      color: #666
    .button-list
      padding: .1rem .6rem .1rem .1rem
      overflow : hidden
      .button-wrap
        box-sizing : border-box
        float : left
        width : 33.33%
        text-align : center
        padding: .1rem
        .button
          border: .02rem solid #ccc
          border-radius : .04rem
          padding: .1rem 0
    .item-list
      .item
        line-height : .76rem
        padding-left : .2rem
</style>
