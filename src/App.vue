<script setup>
import { ref } from 'vue';
import Forms from './components/FormsComp.vue';
import Response from './components/ResponseComp.vue';

const perfil = ref({
    nome: '',
    email: '',
    dataNasc: '',
    endereco: '', 
    cidade: '',
})

function adicionar(copiaPerfil) {
    perfil.value = copiaPerfil
}
// tera que ter uma funcao adicionar para copiar os dados
// tem que ter uma variavel reativa para guardar os dados copiados
// esses dados devem ser enviados para o Response via props

</script>

<template>
    <hr>
    <div>
        <Forms @adicionar="adicionar" />
    </div>
    <hr>
    <div>
        <Response />
    </div>
    <hr>
</template>

<style scoped></style>
