<script>
import { store } from '../store.js';
import CardItem from './CardItem.vue';

export default {
  name: 'AppMain',

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
    <div class="container">

        
      <h2>
         {{'Found ' + store.cards.length + ' cards' }}
      </h2>

      <div 
        class="cards-container"
      >
          
        <CardItem
          v-for="currentCard in store.cards"
          :card="currentCard"
        ></CardItem>

      </div>

    </div>
    
  </main>

</template>

<style lang="scss">

@use '../styles/variables' as *;

main {
  max-width: 1500px;

  margin: 0 auto;
  background-color: white;

  .container {
    padding: 60px;

    background-color: transparent;

    h2 {
        padding: 30px;
        font-size: 1.2em;

        background-color: #212529;
        color: white;

        &.hidden {
          display: none;
        }
    }

    .cards-container {
      display: flex;
      flex-wrap: wrap;
      gap: $cardsGap;

    }

  }

}

</style>