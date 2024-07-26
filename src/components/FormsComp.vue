<script setup>
import { reactive } from 'vue';


const titulo = 'Formulário Pessoal';
const emit = defineEmits(['adicionar']);
const cadastro = reactive({
  nome: ' ',
  email: ' ',
  senha: ' ',
  confirmacaoSenha: ' ',
  dataNasc: null,
  endereco: ' ',
  cidade: ' ',
  
});


function salvar() { // certo
  if (cadastro.nome === '' || cadastro.senha === '') {
    alert('Os campos nome e senha são obrigatórios');
    return;
  }
  else if (cadastro.senha !== cadastro.confirmacaoSenha) {
    alert('Senha errada')

  }
  else {
    emit('adicionar', { ...cadastro });
  }

}


const estado = [{ // certo

  nome: 'Acre',
  sigla: 'AC'
}, {
  nome: 'Alagoas',
  sigla: 'AL'
},
{
  nome: 'Macapá',
  sigla: 'AP'
}, {
  nome: 'Amazonas',
  sigla: 'AM'
}
  , {
  nome: 'Bahia',
  sigla: 'BA'
}
  , {
  nome: 'Ceará',
  sigla: 'CE'
}
  , {
  nome: 'Distrito Federal',
  sigla: 'DF'
},
{
  nome: 'Espirito Santo',
  sigla: 'ES'
},
{
  nome: 'Goiáis',
  sigla: 'GO'
},
{
  nome: 'Maranhão',
  sigla: 'MA'
},
{
  nome: 'Mato Grosso',
  sigla: 'MT'
},
{
  nome: 'Mato Grosso do Sul',
  sigla: 'MS'
},
{
  nome: 'Minas Gerais',
  sigla: 'MG'
},
{
  nome: 'Pará',
  sigla: 'PA'
},
{
  nome: 'Paraíba',
  sigla: 'PB'
},
{
  nome: 'Paraná',
  sigla: 'PR'
},
{
  nome: 'Pernambuco',
  sigla: 'PE'
},
{
  nome: 'Piauí',
  sigla: 'PI'
},
{
  nome: 'Rio de Janeiro',
  sigla: 'RJ'
},
{
  nome: 'Rio Grande do Norte',
  sigla: 'RN'
},
{
  nome: 'Rio Grande do Sul',
  sigla: 'RS'
},
{
  nome: 'Rondônia',
  sigla: 'RO'
},
{
  nome: 'Roraima',
  sigla: 'RR'
},
{
  nome: 'Santa Catarina',
  sigla: 'SC'
},
{
  nome: 'Tocantis',
  sigla: 'TO'
},
{
  nome: 'São Paulo',
  sigla: 'SP'
}];
</script>

<template>

  <body>
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
        <input type="date" v-model="cadastro.dataNasc" placeholder="Digite sua data de nascimento" />
      </div>

      <div class="container">
        <label for="address">Endereço</label>
        <input type="text" v-model="cadastro.endereco" placeholder="Digite seu endereço" />
      </div>
      
      <div class="container">
        <label for="city">Cidade</label>
        <input type="text" v-model="cadastro.cidade" placeholder="Digite sua cidade" />
      </div>

      <label for="">Selecione seu Estado:</label>

      <div class="container">
        <select name="estado" id="estado" class="form-control" v-model.lazy="estado.sigla">
          <option v-for="(item, index) in estado" :value="item.sigla" :key="index.sigla"> {{ item.nome }} ({{ item.sigla}})
          </option>
        </select>
      </div>

      <div class="caixas">
        <input type="checkbox" class="java" value="java">Java
        <input type="checkbox" class="php" value="php">PHP
        <input type="checkbox" class="javaScript" value="javaScript">javaScript
        <input type="checkbox" class="python" value="python">Python
      </div>

      <div class="container">
        <label for="hobby">Hobbies do seu tempo livre:</label>
        <input type="text" v-model="hobbies" placeholder="Digite seu hobbie " />
      </div>
      <div class="container">
        <label for="biografia">Biografia:</label>
        <input type="text" v-model="biografia" placeholder="Digite sua biografia " />
      </div>

     <button @click="salvar">Salvar</button>
    </form>
  </body>
</template>

<style scoped>
body {
  font-family: Arial, Helvetica, sans-serif;
  background-color: rgb(92, 169, 214);
  margin-left: 25%;
  margin-right: 25%;
  border-radius: 15px;
}

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
  border-radius: 5px;
}

label {
  font-weight: bold;
  color: #222;
}

.caixas {
  display: flex;
  justify-content: center;
  font-size: 15px;
  padding: 0px 20px;
  gap: 10px;
}

.botao {
  background-color: rgb(207, 207, 216);
  padding: 8px;
  margin: 10px;
  border-radius: 5px;
}
</style>
