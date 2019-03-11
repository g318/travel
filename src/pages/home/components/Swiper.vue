<template>
<div class="wrapper">
<swiper :options="swiperOption">

    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" alt="">
    </swiper-slide>

    <div class="swiper-pagination"  slot="pagination"></div>

  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data() {
      return {
        swiperOption: {
          pagination: '.swiper-pagination'
        },
        swiperList: [
          {
            id:'0001',
            imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg'
          },
          {
            id:'0002',
            imgUrl: 'https://imgs.qunarzz.com/p/tts5/1811/32/f6d4cd1fdc82a102.jpg_r_390x260x90_ce636520.jpg'
          },
        ]
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
