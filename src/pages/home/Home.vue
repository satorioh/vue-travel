<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
  </div>

</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'

export default {
  name: 'Home',
  components: {
    'home-header': HomeHeader,
    'home-swiper': HomeSwiper
  }
}
</script>

<style>

</style>
