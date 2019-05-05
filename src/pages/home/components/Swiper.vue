<template>
    <div class="warpper">
        <swiper :options="swiperOption" v-if="showSwiper">
            <swiper-slide v-for="item in list" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl" alt>
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    props: {
        list: Array
    },
    data() {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true,
                autoplay: true,
            }
        }
    },
    computed: {
        showSwiper() {
            return this.list.length;
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
        padding-bottom: 32%
        //---高度相对于width的写法---
        .swiper-img 
            width: 100%
</style>