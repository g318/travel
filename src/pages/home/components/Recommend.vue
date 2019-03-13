<template>
    <div>
        <div class="title">热销推荐</div>
<ul>
    <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <!-- <div class="item-img-wrapper"> -->
            <img class="item-img" :src="item.imgUrl" alt="">
        <!-- </div> -->
        <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
        </div>
    </li>
</ul>
        </div>
        
</template>

<script>
export default {
    name: 'HomeRecommend',
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
    .item
        overflow hidden
        display flex
        height 1.9rem
        .item-img
            width 1.7rem
            height 1.7rem
            padding .1rem
        .item-info
            flex 1
            padding .1rem
            min-width 0
            .item-title
                line-height .5rem
                font-size .32rem
                ellipsis()
            .item-desc
                line-height .4rem
                color #ccc
                ellipsis()
            .item-button
                margin-top .16rem
                background #ff9300
                padding .1rem
                border-radius .06rem
                line-height .44rem
                // color #ccc
        
</style>