<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hot="hotCities" :alpha="alpha"></city-list>
    <alphabet :alpha="cities" @change="handleClick"></alphabet>
  </div>
</template>

<script>
import axios from "axios";
import CityHeader from "./components/Header";
import CitySearch from "./components/Search";
import CityList from "./components/List";
import Alphabet from "./components/Alphabet";
export default {
  name: "City",
  components: {
    CityHeader,
    CitySearch,
    CityList,
    Alphabet
  },
  data() {
    return {
      cities: {},
      hotCities: [],
      alpha: ""
    };
  },
  methods: {
    getCityInfo() {
      axios.get("/api/city.json").then(this.handleCityInfoSucc);
    },
    handleCityInfoSucc(res) {
      res = res.data;
      if (res.ret && res.data) {
        const data = res.data;
        this.cities = data.cities;
        this.hotCities = data.hotCities;
      }
    },
    handleClick(e) {
      this.alpha = e;
    }
  },
  mounted() {
    this.getCityInfo();
  }
};
</script>

<style lang='stylus' scoped>
</style>
