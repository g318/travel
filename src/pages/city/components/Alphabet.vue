<template>
    <ul class="list">
       <li class="item" v-for="(item, index) in cities" :key="index">{{index}}</li>
    </ul>
</template>

<script>
export default {
    name: 'CityAlphabet',
    props: {
        cities:Object
    },
}
</script>
<style lang="stylus" scoped>
    @import '~styles/varibles.styl';
    .list
        display flex
        flex-direction column
        justify-content center
        position absolute
        top 1.58rem
        bottom 0
        right 0
        width .4rem
        .item
            text-align center
            line-height .4rem
            color $bgColor
        // overflow hidden
        // height $headerHeight
        // line-height $headerHeight
        // text-align center
        // color #fff
        // background $bgColor
        // font-size .32rem
        // .header-back
        //     position absolute
        //     top 0
        //     left 0
        //     width .64rem
        //     text-align center
        //     font-size .4rem
        //     color #fff
</style>