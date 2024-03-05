<script>
import AppNav from './components/AppNav.vue';
import AppCards from './components/AppCards.vue';
import {store} from './store.js';
import AppSearch from './components/AppSearch.vue';

import axios from 'axios';

export default{
  components: {
    AppCards,
    AppNav,
    AppSearch,
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
  <AppSearch></AppSearch>
  <AppCards></AppCards>
  

</template>

<style lang="scss">
@use './styles/general' as *;

</style>
