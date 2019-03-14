<template>
    <ul class="list">
       <li class="item"
        v-for="item in letters" 
        :key="item"
        :ref='item'
        @click="handleLetterClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        >{{item}}</li>
    </ul>
</template>

<script>
export default {
    name: 'CityAlphabet',
    props: {
        cities:Object
    },
    computed: {
        letters(){
            const letters = []
            for (let i in this.cities) {
                letters.push(i)
            }
            return letters
        }
    },
    data(){
        return {
            touchStatus: false,
            startY: 0,
            timer: null
        }
    },
    updated (){
        this.startY = this.$refs['A'][0].offsetTop
    },
    methods: {
        handleLetterClick (e){
            this.$emit('change',e.target.innerText)
        },
        handleTouchStart (){
            this.touchStatus = true
        },
        handleTouchMove (e){
            if(this.touchStatus == true){
                if(this.timer){
                    clearTimeout(this.timer)
                }
                this.timer = setTimeout(() => {
                    const touchY = e.touches[0].clientY - 79
                    const index = Math.floor((touchY - this.startY) / 20)
                    if(index >= 0 && index < this.letters.length){
                        this.$emit('change',this.letters[index])
                    }
                },16)
            }
        },
        handleTouchEnd () {
            this.touchStatus = false
        }
    }
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