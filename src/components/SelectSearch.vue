<script>
import CardNumber from './CardNumber.vue';

import { store } from '../store.js';

export default {
  name: 'SelectSearch',

  data() {
    return {
      store,

    };
  },

  components: {
    CardNumber,
  },  

};

</script>

<template>
    <div class="container-select">
        <!-- Con il v-model mi salvo l'archetype selezionato -->
        <!-- Con il change mi chiamo il metodo -->
        <select 
          name="search-for-type" id="card-select"
          @change="$emit('search')"
          v-model="store.filterArchetype"
        >
          <option value="" selectedIndex="-1">Select a type!</option>
          <option 
            v-for="type in store.filteredCards"
            :value="type.archetype_name"
          >
            {{ type.archetype_name }}
          </option>
        </select>
        <CardNumber></CardNumber>
    </div>
</template>



<style lang="scss">
@use '../styles/variables' as *;

.container-select {
    display: flex;
    justify-content: space-between;
    align-items: center;

    margin: 0 auto;
    max-width: 1500px;

    margin-bottom: 35px;

    select {
        padding: 10px;

        option {
            font-size: 1em;
        }

    }
}
</style>