<script setup>
import {defineProps} from 'vue';

 
const cadastro = defineProps({
  {nome: ''},
  {email: ''},
  {senha: ''},
  {confirmacaoSenha: ''},
  {dataNasc: ''},
  {endereco: ''},
  {cidade: ''}
});
</script>


<template>
<div v-for="cadastro in adicionar ">
    <h1>title</h1>
    {{ nome }}
    {{ email }}
    {{ dataNasc }}
    {{ endereco }}
    {{ cidade }}

</div>
</template>

<style scoped>

</style>