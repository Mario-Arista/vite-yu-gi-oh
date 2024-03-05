<script>

import { store } from '../store.js';

export default {
  name: 'SelectSearch',

  data() {
    return {
      store,

    };
  },

};

</script>

<template>
    <div class="container">

        <select name="search-for-type" id="card-select">

            <option  value="">Select the type!</option>
            <option 
                v-for="type in store.filteredCards"
                :value="type.archetype_name"
            >
                {{ type.archetype_name }}
            </option>
            
        </select>
                
        
    </div>

</template>



<style lang="scss" scoped>

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