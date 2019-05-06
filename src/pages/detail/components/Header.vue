<template>
  <div>
    <div class="header">
      <div class="header-abs"></div>
      <div class="header-fixed"></div>
    </div>
  </div>
</template>

<script>
import CommonGallary from "common/gallary/Gallary";
export default {
  name: "DetailHeader"
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header-abs {
  position: absolute;
  left: 0.2rem;
  top: 0.2rem;
}
</style>