<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item of hot" :key="item.id">
            <div class="button" @click="handleCityClick(item.name)">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div
          class="item-list"
          v-for="value in item"
          :key="value.id"
          @click="handleCityClick(value.name)"
        >
          <div class="item border-bottom">{{value.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";
import Bscroll from "better-scroll";
export default {
  name: "CityList",
  computed: {
    ...mapState(["city"])
  },
  props: {
    cities: Object,
    hot: Array,
    alpha: String
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  },
  methods: {
    handleCityClick(city) {
      this.changeCity(city);
      this.$router.push("/");
    },
    ...mapActions(["changeCity"])
  },
  watch: {
    alpha() {
      if (this.alpha) {
        const element = this.$refs[this.alpha][0];
        this.scroll.scrollToElement(element);
      }
    }
  }
};
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl';

.border-topbottom {
  &:before {
    border-color: #ccc;
  }

  &:after {
    border-color: #ccc;
  }
}

.border-bottom {
  &:before {
    border-color: #ccc;
  }
}

.list {
  position: absolute;
  overflow: hidden;
  top: 1.68rem;
  bottom: 0;
  left: 0;
  right: 0;

  .title {
    line-height: 0.54rem;
    background: #eee;
    padding-left: 0.2rem;
    color: #666;
    font-size: 0.26rem;
  }

  .button-list {
    overflow: hidden;
    padding: 0.1rem 0.6rem 0.1rem 0.1rem;

    .button-wrapper {
      float: left;
      width: 33.33%;

      .button {
        text-align: center;
        padding: 0.1rem 0;
        margin: 0.1rem;
        border: 0.02rem solid #ccc;
        border-radius: 0.06rem;
      }
    }
  }

  .item-list {
    .item {
      line-height: 0.76rem;
      padding-left: 0.2rem;
    }
  }
}
</style>