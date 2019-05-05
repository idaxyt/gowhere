<template>
    <div class='search'>
        <input class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
  </div>
</template>

<script>
export default {
  name: "CitySearch",
  props: {
      city: String
  }
};
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl';
    .search 
        height: .72rem;
        padding: .1rem
        background: $bgColor;
        .search-input
            box-sizing: border-box
            width: 100%;
            line-height : .62rem;
            height: .62rem;
            text-align: center;
            color: #666;
            border-radius: .06rem;
            padding: 0 .1rem


</style>

