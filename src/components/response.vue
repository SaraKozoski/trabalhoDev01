<script setup>
defineProps(['adicionar']);
</script>


<template>
<div>
    <h1>
        
    </h1>
    <ul v-for="cadastro in adicionar" :key="cadastro.id" >
        <li>{{ cadastro.nome }}</li>
        <li>{{ cadastro.email }}</li>
        <li>{{ cadastro.data }}</li>
        <li  @click= "$emit(cadastro.id)" > a </li>
      
    </ul>
</div>
</template>

<style scoped>

</style>