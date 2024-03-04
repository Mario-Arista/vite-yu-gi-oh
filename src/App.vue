<script>

import axios from 'axios';

import { store } from './store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  // Import
  components: { AppHeader, AppMain },

  data() {
    // Dati
    return {
      cards: [],
      store
    };
  },

  // Created method
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0')
      .then(res => {
        this.store.cards = res.data;
      })
      .catch(error => {
        console.error('Errore durante il recupero delle carte:', error);
      });
  }
}

</script>

<template>

<AppHeader></AppHeader>
<AppMain></AppMain>


</template>

<style lang="scss">

</style>
