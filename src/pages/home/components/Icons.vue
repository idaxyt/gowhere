<template>
    <div class="icons">
        <swiper :options='swiperOption'>
            <swiper-slide>
                <div class='icon'>
                    <div class="icon-img">
                        <img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png" />
                    </div>
                    <p class="icon-desc">热门景点</p>
                </div>
            </swiper-slide>
            <swiper-slide>
                <div class='icon'>
                    <div class="icon-img">
                        <img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png" />
                    </div>
                    <p class="icon-desc">热门景点</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeIcons',
    data() {
        return {
            swiperOption: {
                loop: true
            }
        }
    }
}
</script>

<style lang="stylus" scoped>
    @import  '~styles/varibles.styl'
    .icons
        overflow: hidden
        width: 100%
        height: 0
        padding-bottom: 50%
    .icon
        position: relative
        overflow: hidden
        float: left
        width: 25%
        height: 0
        padding-bottom: 25%
        .icon-img
            position: absolute
            top: 0
            left: 0
            right: 0
            bottom: 0.44rem
            box-sizing: border-box
            padding: .1rem
            .icon-img-content
                //居中
                display: block
                margin: 0 auto
                //居中
                height: 100%
        .icon-desc
            position: absolute 
            left: 0
            right: 0
            bottom: 0
            height: 0.44rem
            line-heigh: 0.44rem
            color: $darkTextColor
            text-align: center
</style>