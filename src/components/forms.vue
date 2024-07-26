<script setup>
import { reactive, ref } from 'vue';
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
const estado = ref([
  "AC", "AL", "AP", "AM", "BA", "CE", "DF", "ES", "GO", "MA", "MT", "MS", "MG", "PA", "PB", "PR",
   "PE", "PI", "RJ", "RN","RS","RO","RR","SC","SE","SC","TO"])
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
      <input type="password" v-model="cadastro.senha" placeholder="Digite sua Senha" />
    </div>
    <div class="container">
      <label for="password">Confirme sua Senha</label>
      <input type="password" v-model="cadastro.confirmacaoSenha" placeholder="Digite sua Senha" />
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
      <label for="">Selecione seu estado:</label>
      <div class="ES">
        <select :id="type" v-model="perfil.estado">
          <option disabled value="Es">Selecione um estado</option>
          <option v-for="(estados, index) in estado" :key="index" :value="estado.sigla">
            {{ estado.nome }}
          </option>
        </select>
      </div>
    </div>

    <div class="container">
      <label for="language">Linguagem que voce usa:</label>
      <input type="text" v-model="linguagem" placeholder="Digite a linguagem" />
    </div>
    <div class="container">
      <label for="hobby">Hobbies do seu tempo livre:</label>
      <input type="text" v-model="hobbies" placeholder="Digite seu hobbie " />
    </div>
    <div class="container">
      <label for="biografia">Biografia:</label>
      <input type="text" v-model="biografia" placeholder="Digite sua biografia " />
    </div>
    <button type="submit">Salvar</button>

  </form>

</template>

<style scoped>
.title {
  margin: auto;
  text-align: center;
  color: rgb(9, 9, 148);
}

#form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  align-items: center;

  margin-bottom: 20px;
  gap: 20px;
}

.container input {
  text-align: center;
}

.container {
  display: flex;
  flex-direction: column;
  width: 40%;
}

label {
  font-weight: bold;
  color: #222;
}

.submit {
  font-weight: bold;
  border: 1px solid #222;
  font-size: 10px;
  padding: 5px;
  margin: 0 auto;
}
</style>
