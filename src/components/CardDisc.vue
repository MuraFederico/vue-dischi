<template>

  <div class="col">
    <div class="card-disc p-3 text-center">
    <div class=" container-poster">
      <img :src="cardData.poster" :alt="cardData.title" class="img-fluid">
    </div>
    <h2 class="fs-3 m-3">{{ cardData.title }}</h2>
    <h3 class="fs-5 m-0">{{ cardData.author }}</h3>
    <p class="fs-6 m-0">{{ cardData.year }}</p>
    </div>
  </div>

</template>

<script>
export default {
  name: 'CardDisc',
  props: {
    cardData: Object,
  },
};
</script>

<style lang="scss" scoped>
  .card-disc {
    max-width: 330px;
    height: 100%;
    background-color: #2e3a46;
    color: white;
  }
  .container-poster {
    max-width: 300px;
  }
</style>>
