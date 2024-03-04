<script>
import AppCards from './components/AppCards.vue';
import {store} from './store.js';

import axios from 'axios';

export default{
  components: {AppCards},

  data(){
    return{
      store,

    }
  },

  

  created(){
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then(res =>{
      this.store.cards = res.data.data

    })
  }

 

}


</script>

<template>

<AppCards></AppCards>

</template>

<style lang="scss">
@use './styles/general' as *;



</style>
