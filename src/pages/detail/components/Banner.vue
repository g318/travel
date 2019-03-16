<template>
  <div>
    <div class="banner" @click="handleBannerClick"> 
      <img
        class="banner-img"
        src="https://imgs.qunarzz.com/p/tts8/1811/c2/a690db98189f0602.jpg_r_390x260x90_b7f98bcc.jpg"
        alt
      >
      <div class="banner-info">
        <div class="banner-title">ffdfsdfsd地方fsdf</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>39
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from "common/gallary/Gallary";

export default {
  name: "DetailBanner",
  data() {
    return {
      showGallary: false,
      imgs: [
        "https://imgs.qunarzz.com/p/tts8/1811/c2/a690db98189f0602.jpg_r_390x260x90_b7f98bcc.jpg",
        "https://imgs.qunarzz.com/p/tts8/1811/c2/a690db98189f0602.jpg_r_390x260x90_b7f98bcc.jpg",
        "https://imgs.qunarzz.com/p/tts8/1811/c2/a690db98189f0602.jpg_r_390x260x90_b7f98bcc.jpg"
      ]
    };
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
};
</script>

<style lang="stylus" scoped>
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;

  .banner-img {
    width: 100%;
  }

  .banner-info {
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: 0.6rem;
    color: #fff;
  }

  // background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
  .banner-title {
    flex: 1;
    font-size: 0.32rem;
    padding: 0 0.2rem;
  }

  .banner-number {
    height: 0.32rem;
    line-height: 0.32rem;
    margin-top: 0.14rem;
    padding: 0 0.4rem;
    border-radius: 0.2rem;
    background: rgba(0, 0, 0, 0.8);
    font-size: 0.24rem;

    .banner-icon {
      font-size: 0.24rem;
    }
  }
}
</style>
