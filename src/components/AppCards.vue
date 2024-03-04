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
    <main>

        <div class="container">
    
            <div class="card-count">
                Found {{ store.cards.length }} cards
    
            </div>
    
            <ul>
                <CardItem
                v-for="currentCard in store.cards"
                :card="currentCard"
                :cardImg="currentCard.card_images[0]">
                </CardItem>
                
            </ul>
    
        </div>


    </main>

</template>

<style lang="scss">
@use '../styles/variables' as *;

main{
    padding-top: 125px;

    background-color: $primaryBg;
    
}

.container{

    padding: 70px;

    background-color: white;

    .card-count{
        padding: 30px;
        
        font-weight: bold;
        font-size: 20px;

        color: white;
        background-color: $secondaryBg;
    }

}

ul{
    display: flex;
    flex-wrap: wrap;
    gap: $cardsGapY $cardsGapX  ;
}



</style>