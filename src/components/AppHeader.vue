<script>

export default {
  name: 'AppHeader'
}

</script>

<template>

  <header>
    <img src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="">
    <h1>YU-Gi-Oh Api</h1>
  </header>

</template>

<style lang="scss">

header {
    display: flex;
    align-items: center;

    color: black;
    background-color: white;

    // test
    margin-bottom: 50px;
    
    img {
        width: 120px;
        height: auto;
        padding: 0px 25px;

    }
    h1 {
        font-size: 2.8em;
        font-weight: 400;
        padding-top: 20px;
        padding-bottom: 20px;

    }
}
</style>