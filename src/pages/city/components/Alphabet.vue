<template>
  <ul class="list">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      :ref="item"
      @click="handleClick"
      @touchstart="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
    >{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: "Alphabet",
  props: {
    alpha: Object
  },
  computed: {
    letters() {
      const letters = [];
      for (let i in this.alpha) {
        letters.push(i);
      }
      return letters;
    }
  },
  data() {
    return {
      touchStatus: false
    };
  },
  methods: {
    handleClick(e) {
      this.$emit("change", e.target.innerText);
    },
    handleTouchStart() {
      this.touchStatus = true;
    },
    handleTouchMove(e) {
      if (this.touchStatus) {
        const startY = this.$refs["A"][0].offsetTop;
        const touchY = e.touches[0].clientY - 81;
        const index = Math.floor((touchY - startY) / 20);
        if (index >= 0 && index < this.letters.length) {
          this.$emit("change", this.letters[index]);
        }
      }
    },
    handleTouchEnd() {
      this.touchStatus = false;
    }
  }
};
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl';

.list {
  // 垂直方向上居中
  display: flex;
  flex-direction: column;
  justify-content: center;
  // 垂直方向上居中
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;

  .item {
    line-height: 0.4rem;
    color: $bgColor;
    text-align: center;
  }
}
</style>
