<template>
  <div>
    <div class="banner">
      <img
        class="banner-img"
        :src="bannerImg"
        alt
        @click="handleBannerClick"
      >
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number">
          <i class="iconfont iconimg"></i>{{this.bannerImgs.length}}
        </div>
      </div>
      <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
  </div>
</template>

<script>
import CommonGallary from "common/gallary/Gallary";
export default {
  name: "DetailBanner",
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data() {
    return {
      showGallary: false
    };
  },
  components: {
    CommonGallary
  },
  methods: {
    handleBannerClick() {
      this.showGallary = true;
    },
    handleGallaryClose() {
      this.showGallary = false;
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;

  .banner-img {
    width: 100%;
  }

  .banner-info {
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: 0.6rem;
    color: #fff;
    // 背景渐变色
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));

    .banner-title {
      flex: 1;
      font-size: 0.28rem;
      padding: 0 0.2rem;
    }

    .banner-number {
      height: 0.32rem;
      margin-top: 0.08rem;
      padding: 0 0.4rem;
      line-height: 0.32rem;
      border-radius: 0.2rem;
      font-size: 0.24rem;
      background: rgba(0, 0, 0, 0.8);
    }

    .iconimg {
      font-size: 0.24rem;
    }
  }
}
</style>