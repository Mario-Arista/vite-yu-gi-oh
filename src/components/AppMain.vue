<script>
import { store } from '../store.js';
import CardItem from './CardItem.vue';

export default {
  name: 'AppMain', // Definizione del nome del componente
  components: {
    CardItem,
  },

  data() {
    return {
      store,
    };
  },

};

</script>

<template>

  <main>
    <CardItem></CardItem>
  </main>

</template>

<style lang="scss">

main {
  color: white;
  background-color: red;
}

</style>