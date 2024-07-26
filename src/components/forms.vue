<script setup>
import { reactive } from 'vue';
const titulo = 'Formulário Pessoal';
const emit = defineEmits(['adicionar']);
const cadastro = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmacaoSenha: '',
  dataNasc: '',
  endereco: '',
  cidade: ''
})
function salvar() {
  if (cadastro.nome === '' || cadastro.senha === '') {
    alert('Os campos nome e senha são obrigatórios');
    return;
  }
  emit('adicionar', { ...cadastro });
}
</script>

<template>
  <div class="title">
    <h1>{{ titulo }}</h1>
  </div>
  <form id="form" @submit.prevent="salvar">
    <div class="container">
      <label for="name">Nome</label>
      <input type="text" v-model="cadastro.nome" placeholder="Digite seu nome" />
    </div>

    <div class="container">
      <label for="email">E-mail</label>
      <input type="text" v-model="cadastro.email" placeholder="Digite seu E-mail" />
    </div>
    <div class="container">
      <label for="password">Senha</label>
      <input type="text" v-model="cadastro.senha" placeholder="Digite sua Senha" />
    </div>
    <div class="container">
      <label for="password">Confirme sua Senha</label>
      <input type="text" v-model="cadastro.confirmacaoSenha" placeholder="Digite sua Senha" />
    </div>
    <div class="container">
      <label for="date">Data de nascimento</label>
      <input type="text" v-model="cadastro.dataNasc" placeholder="Digite sua data de nascimento" />
    </div>
    <div class="container">
      <label for="address">Endereço</label>
      <input type="text" v-model="cadastro.endereco" placeholder="Digite seu endereço" />
    </div>
    <div class="container">
      <label for="city">Cidade</label>
      <input type="text" v-model="cadastro.cidade" placeholder="Digite sua cidade" />
    </div>
    <div class="container">
      <label for="ES">Selecione seu estado:</label>
      <select name="ES" id="estado" v-model="cadastro.estado">
        <option value="">AC </option>
        <option value="">AL</option>
        <option value="">AP</option>
        <option value="">AM</option>
        <option value="">BA</option>
        <option value="">CE</option>
        <option value="">DF</option>
        <option value="">ES</option>
        <option value="">GO</option>
        <option value="">MA</option>
        <option value="">MT</option>
        <option value="">MS</option>
        <option value="">MG</option>
        <option value="">PA</option>
        <option value="">PB</option>
        <option value="">PR</option>
        <option value="">PE</option>
        <option value="">PI</option>
        <option value="">RJ</option>
        <option value="">RN</option>
        <option value="">RS</option>
        <option value="">RO</option>
        <option value="">RR</option>
        <option value="">SC</option>
        <option value="">SP</option>
        <option value="">SE</option>
        <option value="">TO</option>
      </select>
    </div>
    <button type="submit">Salvar</button>
  </form>
</template>

<style scoped>
.title {
  margin: auto;
  text-align: center;
  color: rgb(124, 124, 206);
}
</style>
