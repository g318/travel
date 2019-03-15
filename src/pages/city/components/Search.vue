<template>
<div>
    <div class="search">
<input v-model="keyword" class="search-input" type="text" placeholder="输入城市名">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
        <ul>
            <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
            <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
        </ul>
</div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  props : {
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
    handleCityClick (city) {
      // this.$store.commit('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  computed: {
    hasNoData() {
        return !this.list.length
    }
  },
  watch: {
    keyword () {
        // console.log(this.cities)
        if(this.timer){
                clearTimeout(this.timer)
            }
        if(!this.keyword){
            this.list = []
            return
        }
            this.timer = setTimeout(() => {
                const result = []
                for (let i in this.cities){
                    this.cities[i].forEach((value)=>{
                        if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
                            result.push(value)
                        }
                    })
                }
                this.list = result
            },100)
    }
  },
  mounted (){
      this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>
<style lang="stylus" scoped>
    @import '~styles/varibles.styl';
    .search
        height .72rem
        padding 0 .1rem
        background $bgColor
        .search-input
            box-sizing border-box
            height .64rem
            line-height .64rem
            width 100%
            text-align center
            border-radius .06rem
            color #666
            padding 0 .1rem
    .search-content
        z-index 1
        overflow hidden
        position absolute
        top 1.58rem
        bottom 0
        left 0
        right 0
        background #eeeeee
        .search-item
            color #666
            line-height .62rem
            padding-left .2rem
            background #fff
    //     position relative
    //     overflow hidden
    //     line-height $headerHeight
    //     text-align center
    //     color #fff
    //     font-size .32rem
    //     .header-back
    //         position absolute
    //         top 0
    //         left 0
    //         width .64rem
    //         text-align center
    //         font-size .4rem
    //         color #fff
</style>
