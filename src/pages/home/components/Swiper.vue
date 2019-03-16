<template>
<div class="wrapper">
<swiper :options="swiperOption">
    <swiper-slide v-for="item of list" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" alt="">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props:{
    list:Array
  },
  data() {
      return {
        swiperOption: {
          pagination: '.swiper-pagination'
        },
        
      }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper
  overflow hidden
  width :100%
  height :0
  padding-bottom:32%
  background :#eee
  .swiper-img
    width:100%
</style>
