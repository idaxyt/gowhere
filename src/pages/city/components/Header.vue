<template>
    <div class='header'>
      城市选择
      <router-link to='/'>
        <div><i class="iconfont iconreturn"></i></div>
      </router-link>
    </div>
</template>

<script>
export default {
  name:'CityHeader'
}
</script>

<style lang='stylus' scoped>
  @import '~styles/varibles.styl';
  .header {
    position: relative
    height: $headerHeight;
    overflow: hidden;
    line-height: $headerHeight;
    text-align: center;
    color: #fff;
    background: $bgColor;
    font-size: .32rem;
  }
  .iconreturn
    position: absolute;
    top: 0;
    left: 0;
    width: .64rem;
    text-align: align;
    font-size: .4rem;
    color: #fff
</style>

