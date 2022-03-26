<template>
  <header>
    <i class="fab fa-spotify"></i>
    <select @change="getFilteredArray"
    v-model="selectedGenre" name="genre-filter" id="genre-filter">
      <option v-for="genre in arrGenre" :key="genre" :value="genre">
        {{ genre }}
      </option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'HeaderDisc',
  data() {
    return {
      selectedGenre: '',
      arrFiltered: [],
    };
  },
  props: {
    arrDiscs: Array,
    arrGenre: Array,
  },
  methods: {
    getFilteredArray() {
      this.arrFiltered = [];
      this.arrDiscs.forEach((obj) => {
        if (this.selectedGenre === 'All') {
          this.arrFiltered = this.arrDiscs;
        } else if (obj.genre === this.selectedGenre) {
          this.arrFiltered.push(obj);
        }
      });
    },
  },
  mounted() {
    this.$emit('passArrFiltered', this.arrFiltered);
  },
  updated() {
    this.$emit('passArrFiltered', this.arrFiltered);
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
