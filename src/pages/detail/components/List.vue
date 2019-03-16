<template>
  <div class=''>
      <div class="item" v-for="(item, index) in list" :key="index">
          <div class="item-title border-bottom">
              <div class="item-title-icon">
                  {{item.title}}
              </div>
              <div v-if="item.children" class="item-children">
      <detail-list :list="item.children"></detail-list>
      </div>
          </div>
      </div>
  </div>
</template>

<script>

export default {
  name: 'DetailList',
  props: {
      list: Array
  },
  components: {},
  data() {
    return {}
  },
  computed: {},
  watch: {},
  methods: {

  },
  created() {

},
  mounted() {

  },
  beforeCreate() {}, //生命周期 - 创建之前
  beforeMount() {}, //生命周期 - 挂载之前
  beforeUpdate() {}, //生命周期 - 更新之前
  updated() {}, //生命周期 - 更新之后
  beforeDestroy() {}, //生命周期 - 销毁之前
  destroyed() {}, //生命周期 - 销毁完成
  activated() {}, //如果页面有keep-alive缓存功能，这个函数会触发
  }
</script>
<style lang='stylus' scoped>
//@import url(); 引入公共css类
.item-title-icon
    position: relative
    left: .06rem
    top: .06rem
    display: inline-block
    width: .36rem
    height: .36rem
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
    margin-right: .1rem
    background-size: .4rem 3rem
  .item-title
    line-height: .8rem
    font-size: .32rem
    padding: 0 .2rem
  .item-children
    padding: 0 .2rem

</style>