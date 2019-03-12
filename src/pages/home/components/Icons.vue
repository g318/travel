<template>
  <div class="icons">
<swiper>
    <swiper-slide v-for="(page,index) of pages" :key="index">
    <div class="icon" v-for="item of page" :key="item.id">
      <div class="icon-img">
        <img
          class="icon-img-content"
          :src='item.imgUrl'
          alt
        >
      </div>
      <p class="icon-desc">{{item.desc}}</p>
    </div>
    </swiper-slide>
  </swiper>

  </div>
</template>
<script>
export default {
  name: "HomeIcons",
  data() {
      return {
        iconList: [
          {
            id:'0001',
            imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg',
            desc: '热门景点dddddddddddddd'
          },
          {
            id:'0002',
            imgUrl: 'https://imgs.qunarzz.com/p/tts5/1811/32/f6d4cd1fdc82a102.jpg_r_390x260x90_ce636520.jpg',
            desc: '热门景'
          },
          {
            id:'0003',
            imgUrl: 'https://imgs.qunarzz.com/p/tts9/1710/ee/7d44297c48ebfe02.jpg_r_390x260x90_c3b80ff8.jpg',
            desc: '热门'
          },
          {
            id:'0004',
            imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg',
            desc: '热'
          },
          {
            id:'0005',
            imgUrl: 'https://imgs.qunarzz.com/p/tts5/1811/32/f6d4cd1fdc82a102.jpg_r_390x260x90_ce636520.jpg',
            desc: '热门'
          },
          {
            id:'0006',
            imgUrl: 'https://imgs.qunarzz.com/p/tts9/1710/ee/7d44297c48ebfe02.jpg_r_390x260x90_c3b80ff8.jpg',
            desc: '热门景'
          },
          {
            id:'0007',
            imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg',
            desc: '热门景点'
          },
          {
            id:'0008',
            imgUrl: 'https://imgs.qunarzz.com/p/tts5/1811/32/f6d4cd1fdc82a102.jpg_r_390x260x90_ce636520.jpg',
            desc: '热门景'
          },
          {
            id:'0009',
            imgUrl: 'https://imgs.qunarzz.com/p/tts9/1710/ee/7d44297c48ebfe02.jpg_r_390x260x90_c3b80ff8.jpg',
            desc: '热门'
          },
        ]
      }
  },
  computed:{
      pages (){
          const pages = []
          this.iconList.forEach((item,index)=>{
              const page = Math.floor(index/8)
              if(!pages[page]){
                  pages[page] = []
              }
              pages[page].push(item)
          })
          return pages
      }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';

.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 50%;

  .icon {
    position: relative;
    overflow: hidden;
    float: left;
    height: 0;
    width: 25%;
    padding-bottom: 25%;

    .icon-img {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.1rem;

      .icon-img-content {
        height: 100%;
        display: block;
        margin: 0 auto;
      }
    }

    .icon-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      line-height: 0.44rem;
      height: 0.44rem;
      color: $darkTextColor;
      text-align: center;
      ellipsis()
    }
  }
}
</style>