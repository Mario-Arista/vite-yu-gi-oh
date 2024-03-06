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

 
  created() {

    // Per chaimare API Iniziale
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(res => {
        this.store.cards = res.data.data;
      })
      .catch(error => {
      console.error('Errore durante il recupero delle carte:', error);

    });

    // Per chiamare API per popolare select
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res => {
        this.store.filteredCards = res.data;
      })
      .catch(error => {
      console.error('Errore durante il recupero delle carte:', error);

    });

  },

  methods: {

    // Metodo per cambiare cards nello store in base alla option selezionata 
    searchArchetype() {

      axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=` + this.store.filterArchetype)
        .then(res => {
          this.store.cards = res.data.data;
          this.store.numberOfCards = res.data.meta.total_rows;
        })
        .catch(error => {
          console.error('Errore durante il recupero delle carte:', error);
        });
    },
  },

}

</script>

<template>
  
<AppLoader v-if="! store.cards.length > 0"></AppLoader>

<AppHeader></AppHeader>

<SelectSearch @search="searchArchetype()" ></SelectSearch>

<AppMain></AppMain>


</template>

<style lang="scss">

</style>
