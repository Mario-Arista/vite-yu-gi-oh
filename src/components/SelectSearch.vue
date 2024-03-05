<script>

import { store } from '../store.js';

export default {
  name: 'SelectSearch',

  data() {
    return {
      store,

    };
  },

  methods: {
    searchArchetype() {
        // Evento 'search' con selectedArchetype come argomento/parametro
      this.$emit('search', this.selectedArchetype);
    },
  },


};

</script>

<template>
    <div class="container">

            <!-- Con il v-model mi salvo l'archetype selezionato -->
            <!-- Con il change mi chiamo il metodo -->
        <select name="search-for-type()" id="card-select"
                @change="searchArchetype"
                v-model="selectedArchetype" 
        >
            <option 
                v-for="type in store.filteredCards"
                :value="type.archetype_name"
            >
                {{ type.archetype_name }}
            </option>
            
        </select>
                
        
    </div>

</template>



<style lang="scss">

@use '../styles/variables' as *;

.container {
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