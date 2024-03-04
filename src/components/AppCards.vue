<script>

import CardItem from './CardItem.vue';
import {store} from '../store.js';

export default {
    name: "AppCards",

    components: {CardItem},

    data(){
        return{
            store,
            

        }
    }
}



</script>

<template>

    <ul>
        <CardItem
        v-for="currentCard in store.cards"
        :card="currentCard"
        :cardImg="currentCard.card_images[0]">
        </CardItem>
        
    </ul>

</template>

<style lang="scss">



</style>