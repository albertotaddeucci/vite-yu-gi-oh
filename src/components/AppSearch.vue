<script>


export default {
    name: "AppSearch",

    data(){
        return{
                        

        }
    },

    
}



</script>

<template>

<div class="select-wrapper">
  <select id="mySelect">
    <option value="option1">Option 1</option>
    <option value="option2">Option 2</option>
    <option value="option3">Option 3</option>
  </select>
</div>




</template>

<style lang="scss">
@use '../styles/variables' as *;



.select-wrapper select {
  padding: 20px 30px; 
  
  border: 1px solid #ccc;
  border-radius: 4px;

  font-size: 20px;
  
  background-color: #f1f1f1; 
  cursor: pointer;
}






</style>