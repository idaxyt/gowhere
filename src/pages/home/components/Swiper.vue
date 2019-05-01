<template>
<div class='warpper'>
    <swiper :options="swiperOption">
        <swiper-slide v-for="item in swiperList" :key='item.id'>
            <img class="swiper-img" :src="item.imgUrl" alt="">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
</div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    data() {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true
            },
            swiperList: [{
                id: '0001',
                imgUrl: 'http://source.qunarzz.com/site/images/wns/20190428_qunar_dujia_homepage_3.jpg'
            },{
                id: '0002',
                imgUrl: '//source.qunarzz.com/site/images/wns/20190415_qunar_dujia_homepage_top_banner_1.jpeg'
            },{
                id: '0003',
                imgUrl: 'http://source.qunarzz.com/site/images/wns/20190423_dujia_homepage_top_banner_5.jpg'
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>
    //样式穿透
    .warpper  >>> .swiper-pagination-bullet-active
            background: #fff
    .warpper
        width: 100%
        background: #eee
        //---高度相对于width的写法---或者写height: 25.6vw
        height: 0
        overflow : hidden
        padding-bottom: 25.6%
        //---高度相对于width的写法---
        .swiper-img 
            width: 100%
</style>