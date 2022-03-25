<template>
  <main class="p-5">
    <div class="container">
      <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-xxl-5 g-3">
        <card-disc v-for="disc in arrDiscs" :key="disc.title"
        :cardData="disc"
        />
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import CardDisc from './CardDisc.vue';

export default {
  name: 'MainDisc',
  components: {
    CardDisc,
  },
  data() {
    return {
      arrDiscs: null,
    };
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((res) => {
        this.arrDiscs = res.data.response.map((objDisc) => {
          const obj = {
            poster: objDisc.poster,
            title: objDisc.title,
            author: objDisc.author,
            genre: objDisc.genre,
            year: objDisc.year,
          };
          return obj;
        });
        this.$emit('dataTransfer', this.arrDiscs);
      });
  },
};
</script>

<style lang="scss">
  main {
    min-height: 100vh;
    background-color: #1e2d3b;
  }
</style>>
