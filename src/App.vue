<script>

import axios from 'axios';

import { store } from './store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';

export default {
  // Import
  components: { AppLoader, AppHeader, AppMain },

  data() {
    // Dati
    return {
      store,

    };
  },

  // Created method
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=120&offset=0')
      .then(res => {
        this.store.cards = res.data.data;
      })
      .catch(error => {
        console.error('Errore durante il recupero delle carte:', error);

      });
  }
}

</script>

<template>
  
<AppLoader v-if="! store.cards.length > 0"></AppLoader>

<AppHeader></AppHeader>
<AppMain></AppMain>


</template>

<style lang="scss">

</style>
