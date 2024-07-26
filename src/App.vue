<script setup>
import { ref } from 'vue';
import Forms from './components/FormsComp.vue';
import Response from './components/ResponseComp.vue';

const perfil = ref({})
const resultado = ref(false)

function copiar(copiaPerfil) {
    perfil.value = copiaPerfil
    resultado.value = true
}
</script>

<template>
    
     <hr>
    <div>
        <Forms @adicionar="copiar" />
    </div>
    <hr>
    <div>
        <Response v-if="resultado" :perfil="perfil"/>
    </div>
    <hr>

</template>

<style scoped>

</style>
