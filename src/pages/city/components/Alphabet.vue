<template>
  <ul class="list">
    <li class="item" v-for="(item,index) of cities" :key="index">{{index}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
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
