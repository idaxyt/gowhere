<template>
  <div class="header">
    <div class="header-left">
      <div class="icon-left">
        <i class="iconfont iconreturn"></i>
      </div>
    </div>
    <div class="header-input">
      <i class="iconfont iconsearch"></i> 输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      {{this.city}}
      <i class="iconfont iconarrow"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    city: String
  }
};
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl';

.header {
  display: flex;
  line-height: 0.86rem;
  background: $bgColor;
  color: #fff;

  .header-left {
    width: 0.64rem;
    float: left;

    .icon-left {
      text-align: center;
      font-size: 0.4rem;
    }
  }

  .header-input {
    flex: 1;
    border-radius: 0.1rem;
    background: #ffffff;
    color: #ccc;
    height: 0.64rem;
    line-height: 0.64rem;
    margin-top: 0.12rem;
    margin-left: 0.2rem;
    padding-left: 0.1rem;
  }

  .header-right {
    width: 1.24rem;
    float: right;
    text-align: center;

    .iconarrow {
      margin-left: 0.09rem;
      font-size: 0.24rem;
    }
  }
}
</style>

