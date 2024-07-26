<script setup>

const props = defineProps({
 perfil: Object
});




</script>


<template>
  <div class="container">
   <div v-for="(info, index) in props.perfil" :key="index">{{ info }}</div>
  </div>
  </template>

<style scoped>
  .container{
    margin-left: 25%;
    margin-right: 25%;
    display: grid;
    place-items: center;
    font-size: 20px;
   background-color: rgb(235, 139, 219);
   color: rgb(0, 0, 0);
   border-radius: 15px;
    }
</style>