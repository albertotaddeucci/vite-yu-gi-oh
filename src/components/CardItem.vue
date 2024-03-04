<script>
// import {store} from './store.js';

export default {
    name: "CardItem",

    props: {
        card: Object,
        cardImg: Object
    }
}

</script>

<template>

<li>
    <img :src="cardImg.image_url" alt="">
    <span>{{ card.name }}</span>
</li>

</template>

<style lang="scss">



</style>