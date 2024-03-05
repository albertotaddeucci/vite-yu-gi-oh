<script>
import {store} from '../store.js';


export default {
    name: "AppSearch",

    
    data(){
        return{
           store,    
                    

        }
    },

    
}



</script>

<template>

  <div class="container">

    <div class="select-wrapper">
      <select id="mySelect" v-model="store.selected" @change="$emit('search')">
        <option  v-for="(archetype) in store.archetypes" >{{archetype.archetype_name}}</option>
        
      </select>
    </div>

  </div>





</template>

<style lang="scss">
@use '../styles/variables' as *;



.select-wrapper select {
  margin-top: 40px;
  padding: 20px 30px; 
  
  border: 1px solid #ccc;
  border-radius: 4px;

  font-size: 20px;
  
  background-color: #f1f1f1; 
  cursor: pointer;
}






</style>