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

  methods:{
    searchArch(){
      axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=${store.imgPerPage}&offset=0&archetype=${store.selected}`)
      .then(res =>{
        this.store.cards = res.data.data
        this.store.found = res.data.meta.total_rows

    });
    
  }
},


created(){
  
  axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=${store.imgPerPage}&offset=0`)
  .then(res =>{
    this.store.cards = res.data.data
    
    
    }),

    axios.get(`https://db.ygoprodeck.com/api/v7/archetypes.php`)
    .then(res =>{
      this.store.archetypes = res.data



    })

    
  }

}


</script>

<template>

  <AppNav></AppNav>
  <AppSearch @search="searchArch()"></AppSearch>
  <AppCards></AppCards>
  

</template>

<style lang="scss">
@use './styles/general' as *;

</style>
