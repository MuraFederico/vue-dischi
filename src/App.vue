<template>
  <div id="app">
    <header-disc @passArrFiltered="getArrFiltered" :arrDiscs="arrDiscs" :arrGenre="arrGenre"/>
    <main-disc @dataTransfer="getData" :arrFiltered="arrFiltered"/>
  </div>
</template>

<script>
/* eslint-disable */
import HeaderDisc from './components/HeaderDisc.vue';
import MainDisc from './components/MainDisc.vue';

export default {
  name: 'App',
  components: {
    HeaderDisc,
    MainDisc,
  },
  data() {
    return {
      arrDiscs: [],
      arrGenre: ['All'],
      arrFiltered: [],
    };
  },
  methods: {
    getData(data) {
      this.arrDiscs = data;
    },
    getArrFiltered(data) {
      this.arrFiltered = data;
    },
    getArrGenre() {
      this.arrDiscs.forEach((disc) => {
        if (!this.arrGenre.includes(disc.genre)) {
          this.arrGenre.push(disc.genre);
        }
      });
    },
  },
  mounted() {
    this.getArrGenre();
  },
  updated() {
    this.getArrGenre();
  },
};
</script>

<style lang="scss">
$primary: #1e2d3b;
$secondary: #2e3a46;
@import "../node_modules/bootstrap/scss/bootstrap";

</style>
