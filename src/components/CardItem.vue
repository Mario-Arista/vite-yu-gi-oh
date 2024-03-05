<script>

export default {
  name: 'CardItem',

  props: {
        card: Object,
    },
}

</script>

<template>

  <div class="card">

    <img :src="card.card_images[0].image_url" :alt="card.name">
    <div class="name-card"> {{ card.name }}</div>
    <div class="type-card">{{ card.archetype || 'Not Specified' }}</div>
    
  </div>

</template>

<style lang="scss">

@use '../styles/variables' as *;

.card {
    display: flex;
    flex-direction: column;
    align-items: space-between; 

    width: calc(100% / 5 - $cardsGap / 5 * 4);
    background-color:$primary_color;

    img {

        width: 100%;
        padding-bottom: 30px;
    }

    .name-card {
        min-height: 76px;
        padding-bottom: 40px;

        text-transform: uppercase;
        font-size: 1em;
        font-weight: bold;
        text-align: center;

        color: white;
        
    }
    .type-card {
        padding-bottom: 20px;
        font-size: 1.2em;

        text-align: center;

        color: black;
    }

}

</style>