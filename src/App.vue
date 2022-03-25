<template>
  <div id="app">
    <header-disc :arrDiscs="arrDiscs"/>
    <main-disc @dataTransfer="getData" />
  </div>
</template>

<script>
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
      arrDiscs: null,
    };
  },
  methods: {
    getData(data) {
      this.arrDiscs = data;
    },
  },
};
</script>

<style lang="scss">
$primary: #1e2d3b;
$secondary: #2e3a46;
@import "../node_modules/bootstrap/scss/bootstrap";

</style>
