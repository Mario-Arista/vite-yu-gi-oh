<script>
export default {
    name: 'AppLoader',

}
</script>

<template>

    <div id="loader-wrapper">

        <img src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="logo">
        <div>loading...</div>

    </div>

</template>

<style lang="scss" scoped>

#loader-wrapper {

    position: fixed;
    left: 0;
    top: 0;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    width: 100%;
    height: 100%;

    background-color: black;

    img {

        width: 300px;
    }

    div {
        color: white;
        font-size: 3em;
        font-weight: bold;
    }

}



</style>