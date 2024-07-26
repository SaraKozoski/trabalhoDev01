<script setup>
import {defineProps} from 'vue';

function salvar() {
  if (nome === '' || senha === '') {
    alert('Os campos nome e senha são obrigatórios');
   return; }
  if(senha =! confirmacaoSenha){
    alert('A confirmação de senha está diferente da senha!')
    return; }
  
}
const props = defineProps({
  nome: {
    type: String,
    required: true,
  },
  email: {
    type: String,
  },
  senha: {
    type: Number,
    required: true,
  },
  confirmacaoSenha: {
    type: Number,
    required: true,
  },
  dataNasc: {
    type: Date,
    required: true,
  },
  endereco: {
    type: String,
  },
  cidade: {
    type: String,
  },
});
</script>


<template>
<div>
    {{ nome }}
    {{ email }}
    {{ dataNasc }}
    {{ endereco }}
    {{ cidade }}

</div>
</template>

<style scoped>

</style>