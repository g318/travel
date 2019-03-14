<template>
    <div class="search">
<input class="search-input" type="text" placeholder="输入城市名">
    </div>
</template>

<script>
export default {
    name: 'CitySearch'
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