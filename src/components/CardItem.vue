<script>
import {store} from '../store.js';

export default {
    name: "CardItem",

    props: {
        card: Object,
        cardImg: Object,
        
    },

    data() {
        return {
            store,
            
            
            
        }
    },
    methods: {
        onImgLoad() {
            store.count++ 
                  
            
            return this.isLoaded = true
        },
    },
}

</script>

<template>

<li>
    
    <img  @load="onImgLoad()" :src="cardImg.image_url" alt="">
    <div class="card-text">
        <div class="card-name">{{ card.name }}</div>
        <div class="card-archetype">{{ card.archetype }}</div>

    </div>
</li>

</template>

<style lang="scss">
@use '../styles/variables' as *;


li{
    width: calc(100%/5 - $cardsGapX / 5 * 4);


    text-align: center;

    background-color: $primaryBg;
    color: white;   


    img{
        width: 100%;
    }

    .card-text{
        padding: 30px;

        font-size: 18px;


        .card-name{
            margin-bottom: 30px;
    
            text-transform: uppercase;
            font-weight: bold;
        }
    
        .card-archetype{
            color: black;
        }
    }


}



</style>