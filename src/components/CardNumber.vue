<script>
import {store } from '../store';

export default {
    name: 'CardNumber',

    data() {
        return  {
            store,
        }
    },

}

</script>
 
<template>
    
    <div id="card-total-number"
        :class="{ 'd-none': store.numberOfCards <= 0, 'active': store.numberOfCards > 0 }"
    >
        Il numero totale di carte di questo tipo è: {{ store.numberOfCards }}
    </div>

</template>

<style lang="scss">

#card-total-number {
    background-color: white;
    padding: 8px 12px;
    font-size: .9em;
    font-weight: bold;

    &.active{
        display: block;
    }

    &.d-none {
        display: none;
    }
}

</style>