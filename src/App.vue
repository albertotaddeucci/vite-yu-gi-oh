<script>
import AppNav from './components/AppNav.vue';
import AppCards from './components/AppCards.vue';
import {store} from './store.js';

import axios from 'axios';

export default{
  components: {
    AppCards,
    AppNav,
  },

  data(){
    return{
      store,

    }
  },
 

  created(){

    axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=${store.imgPerPage}&offset=0`).then(res =>{
      this.store.cards = res.data.data

    })
    
  }

 

}


</script>

<template>

  <AppNav></AppNav>
  <AppCards></AppCards>
  

</template>

<style lang="scss">
@use './styles/general' as *;




</style>
