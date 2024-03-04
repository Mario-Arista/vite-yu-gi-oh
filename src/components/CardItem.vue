<script>

export default {
  name: 'CardItem',

  props: {
        SingleCard: Array,
    },
}

</script>

<template>

  <div class="card"
    v-for="currentcard in SingleCard"
  
  >
    <!-- Prima verifico se la carta contiene dati validi prima di visualizzarla -->
    <div v-if="currentcard && currentcard.card_images && currentcard.card_images.length > 0">
        <div v-for="image in currentcard.card_images">
            <img :src="image.image_url" :alt="currentcard.name">
        </div>
        <div class="name-card"> {{ currentcard.name }}</div>
        <div class="type-card">{{ currentcard.archetype || 'Not Specified' }}</div>
    </div>
  </div>

</template>

<style lang="scss">

.card {
    display: flex;
    flex-direction: column;
    align-items: center;

    width: calc(100% / 5 - 30px / 5 * 4);
    background-color: #D48F38;

    img {

        width: 100%;
        padding-bottom: 30px;
    }

    .name-card {
        padding-bottom: 40px;

        text-transform: uppercase;
        font-size: 1em;
        font-weight: bold;
        text-align: center;

        color: white;
        
    }
    .type-card {
        padding-bottom: 20px;
        font-size: 1em;

        text-align: center;

        color: black;
    }

}

</style>