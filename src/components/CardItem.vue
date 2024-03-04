<script>

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
@use '../styles/variables' as *;


li{
    width: calc(100%/5 - $cardsGapX / 5 * 4);
    

    background-color: $primaryBg;
    color: white;

    text-align: center;
    text-transform: uppercase;
    font-weight: bold;


    img{
        width: 100%;
    }

    span{
        padding: 10px;
    }

}



</style>