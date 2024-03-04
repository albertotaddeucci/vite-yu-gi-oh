<script>

export default {
    name: "AppLoader",    
}

</script>

<template>
<div class="loader">
    in caricamento ...
</div>

</template>

<style lang="scss">
@use '../styles/variables' as *;

.loader{
    width: 100%;

    padding: 70px;

    font-size: 30px;
    text-align: center;

    color: white;
    background-color: green;
}


</style>