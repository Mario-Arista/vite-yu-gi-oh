<script>

export default {
  name: 'CardItem',

  props: {
        SingleCard: Array,
    },
}

</script>

<template>

  <div class="card"
    v-for="currentcard in SingleCard"
  
  >
    <div v-for="image in currentcard.card_images">
        <img :src="image.image_url" :alt="currentcard.name">
    </div>
    <div class="name-card"> {{ currentcard.name }}</div>
    <div class="type-card"> {{ currentcard.archetype }}</div>

  </div>

</template>

<style lang="scss">

.card {
    width: calc(100% / 5 - 30px / 6 * 5);
}

</style>