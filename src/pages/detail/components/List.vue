<template>
  <div>
    <div class="item" v-for='(item,index) in list' :key='index'>
      <div class="item-title border-bottom">
        <i class="item-title-icon"></i>{{item.title}}
      </div>
      <div v-if='item.children' class="item-children">
        <detail-list :list='item.children'></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailList",
  data() {
    return {
      
    }
  },
  props: {
    list: Array
  },
  methods: {
    
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.item-title-icon
  position: relative;
  left: .06rem;
  top: .08rem;
  display: inline-block;
  width: .36rem;
  height: .36rem;
  background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
  margin-right: .1rem;
  background-size: .4rem 3rem;
.item-title 
  line-height: .8rem;
  font-size: .3rem;
  padding: 0 .2rem;
.item-children
  padding: 0 .2rem;
</style>