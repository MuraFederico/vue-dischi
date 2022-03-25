<template>
  <header>
    <i class="fab fa-spotify"></i>
    <select name="genre-filter" id="genre-filter">
      <option v-for="disc in getGenre()" :key="disc.genre" :value="disc.genre">
        {{ disc.genre }}
      </option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'HeaderDisc',
  data() {
    return {
      arrGenre: null,
    };
  },
  props: {
    arrDiscs: Array,
  },
  methods: {

  },
  created() {
    this.arrDiscs.forEach((disc) => {
      if (!this.arrGenre.includes(disc.genre)) {
        this.arrGenre.push(disc.genre);
      }
    });
  },
  updated() {
    this.arrDiscs.forEach((disc) => {
      if (!this.arrGenre.includes(disc.genre)) {
        this.arrGenre.push(disc.genre);
      }
    });
  },
};
</script>

<style lang="scss" scoped>
  header {
    background-color: #2e3a46;
    i {
      margin: 1rem;
      font-size: 50px;
      color: #1ed65f;
    }
  }
</style>>
