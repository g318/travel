<template>
    <div>
        <div class="title">周末去哪儿</div>
<ul>
    <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
            <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
        </div>
    </li>
</ul>
        </div>
</template>

<script>
export default {
    name: 'HomeWeekend',
    data () {
        return {
             recommendList: [
                {
                    id: '0001',
                    imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg',
                    title: '水电费sdf电费',
                    desc: '哒哒哒哒哒哒地方大幅度辅导辅导辅导费对方水电费水电费多多多多多撒大声地'
                },
                {
                    id: '0002',
                    imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg',
                    title: '水sdf电费',
                    desc: '哒哒哒哒哒哒地方大幅度辅导辅导辅导费对方水电费水电费多多多多多撒大声地'
                },
                {
                    id: '0003',
                    imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg',
                    title: 'sdf水电费',
                    desc: '哒哒哒哒哒哒地方大幅度辅导辅导辅导费对方水电费水电费多多多多多撒大声地'
                },
                {
                    id: '0004',
                    imgUrl: 'https://imgs.qunarzz.com/p/tts4/1811/82/e20f4bc554cc8902.jpg_r_390x260x90_8686b536.jpg',
                    title: '水电费ds水电费',
                    desc: '哒哒哒哒哒哒地方大幅度辅导辅导辅导费对方水电费水电费多多多多多撒大声地'
                },
            ]
        }
    }       
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';
    .title
        margin-top .1rem
        line-height .8rem
        background #eee
        text-indent .2rem
    .item-img-wrapper
        overflow hidden
        height 0
        padding-bottom 33.9%
        .item-img
            width 100%
    .item-info
        padding .1rem
        .item-title
            line-height .5rem
            font-size .32rem
            ellipsis()
        .item-desc
            line-height .4rem
            color #ccc
            ellipsis()
        
</style>