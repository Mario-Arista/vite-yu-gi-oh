<script>

import axios from 'axios';

import { store } from './store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
import SelectSearch from './components/SelectSearch.vue'

export default {
  // Import
  components: { AppLoader, AppHeader, AppMain, SelectSearch },

  data() {
    // Dati
    return {
      store,

    };
  },

  // Created method
  created() {
    
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(res => {
        this.store.cards = res.data.data;
      })
      .catch(error => {
      console.error('Errore durante il recupero delle carte:', error);

    });

    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res => {
        this.store.filteredCards = res.data;
      })
      .catch(error => {
      console.error('Errore durante il recupero delle carte:', error);

    });

  },

  methods: {

    searchArchetype() {

      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&farchetype=${store.savedArchetype}')
        .then(res => {

          this.store.cards = res.data.data;

        });

      console.log("Ricerca percepita")
    },

  },

}

</script>

<template>
  
<AppLoader v-if="! store.cards.length > 0"></AppLoader>

<AppHeader></AppHeader>

<SelectSearch
  @search="searchArchetype()"
></SelectSearch>

<AppMain></AppMain>


</template>

<style lang="scss">

</style>
