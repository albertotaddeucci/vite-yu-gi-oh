<script>
import CardItem from './CardItem.vue';
import AppLoader from './AppLoader.vue';

import {store} from '../store.js';

export default {
    name: "AppCards",

    components: {CardItem, AppLoader},

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

            <AppLoader 
            v-if="store.count<store.imgPerPage"
            ></AppLoader>

            <div
            v-show="store.count>=store.imgPerPage">
                <div v-show="store.found!=0" class="card-count">
                    Found {{ store.found }} cards
        
                </div>
        
                <ul>
                    <CardItem
                    v-for="currentCard in store.cards"
                    :card="currentCard"                    
                    >
                    </CardItem>
                    
                </ul>


            </div>
    
    
        </div>


    </main>

</template>

<style lang="scss">
@use '../styles/variables' as *;

main{
    padding-block: 50px;
    
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
    
        ul{
            display: flex;
            flex-wrap: wrap;
            gap: $cardsGapY $cardsGapX  ;
        }

    }
}





</style>