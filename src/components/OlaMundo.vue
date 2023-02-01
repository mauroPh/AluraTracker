<template>
    <h1>Olá mundo!</h1>
    <h2> Olá VUE !</h2>
    <img src="@/assets/usar.png"/>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    
    export default defineComponent({
        name:"OlaMundo"
    })
</script>

<style>
   h1{
    color: blue;
   }
</style>


