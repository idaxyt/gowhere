<template>
  <div>
    <div class="title">猜你喜欢</div>
    <ul>
      <router-link
        tag="li"
        :to="'/detail/'+item.id"
        class="item border-bottom"
        v-for="item in list"
        :key="item.id"
      >
        <img class="item-img" :src="item.imgUrl" alt>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  props: {
    list: Array
  },
  data() {
    return {};
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.title {
  margin-top: 0.2rem;
  line-height: 0.8rem;
  text-indent: 0.2rem;
  background: #eee;
}

.item {
  display: flex;
  height: 2.4rem;
  overflow: hidden;
}

.item-img {
  width: 2.2rem;
  height: 2.2rem;
  padding: 0.1rem;
}

.item-info {
  flex: 1;
  padding: 0.1rem;
  min-width: 0;

  .item-title {
    line-height: 0.54rem;
    font-size: 0.32rem;
    ellipsis();
  }

  .item-desc {
    line-height: 0.4rem;
    color: #ccc;
    ellipsis();
  }

  .item-button {
    line-height: 0.44rem;
    margin-top: 0.16rem;
    background: #ff9300;
    padding: 0 0.2rem;
    border-radius: 0.06rem;
    color: #fff;
  }
}
</style>
