<template>
  <div class="container" @click="handleGallaryClick">
    <div class="warpper">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(item,index) in imgs" :key="index">
          <img class="gallary-img" :src="item" alt>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: "CommonGallary",
  props: {
    imgs: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  data() {
    return {
      swiperOptions: {
        pagination: ".swiper-pagination",
        // 修改轮播图底部显示样式
        paginationType: "fraction",
        // 监听父组件或组件dom元素发生变化，自动自我刷新
        observeParents: true,
        observer: true
      }
    };
  },
  methods: {
    handleGallaryClick() {
      this.$emit("close");
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.container >>> .swiper-container {
  overflow: inherit;
}

.container 
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background: #000;
  z-index: 99;

.wrapper 
  width: 100%;
  padding-bottom: 100%;
  height: 0;

.gallary-img {
  width: 100%;
}

.swiper-pagination {
  color: #fff;
  bottom: -1rem;
}
</style>
