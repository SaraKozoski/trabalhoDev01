<script setup>
const nome = 'Formulário Pessoal'
</script>

<template>
  <div class="title">
    <h1>{{ nome }}</h1>
  </div>
  <form id="form">
    <div class="container">
      <label for="name">Nome</label>
      <input type="text" placeholder="Digite seu nome" />
    </div>

    <div class="container">
      <label for="email">E-mail</label>
      <input type="text" placeholder="Digite seu E-mail" />
    </div>
    <div class="container">
      <label for="password">Senha</label>
      <input type="text" placeholder="Digite sua Senha" />
    </div>
    <div class="container">
      <label for="password">Confirme sua Senha</label>
      <input type="text" placeholder="Digite sua Senha" />
    </div>
    <div class="container">
      <label for="date">Data de nascimento</label>
      <input type="text" placeholder="Digite sua data de nascimento" />
    </div>
    <div class="container">
      <label for="address">Endereço</label>
      <input type="text" placeholder="Digite seu endereço" />
    </div>
    <div class="container">
      <label for="city">Cidade</label>
      <input type="text" placeholder="Digite sua cidade" />
    </div>
    <div class="container">
      <label for="ES">Selecione seu estado:</label>
      <select name="ES" id="estado" v-model="estado">
        <option value="">AC </option>
        <option value="">AL</option>
        <option value="">AP</option>
        <option value="">AM</option>
        <option value="">BA</option>
        <option value="">CE</option>
        <option value="">DF</option>
        <option value="">ES</option>
        <optin value="">GO</optin>
        <optin value="">MA</optin>
        <optin value="">MT</optin>
        <optin value="">MS</optin>
        <optin value="">MG</optin>
        <optin value="">PA</optin>
        <optin value="">PB</optin>
        <optin value="">PR</optin>
        <optin value="">PE</optin>
        <optin value="">PI</optin>
        <optin value="">RJ</optin>
        <optin value="">RN</optin>
        <optin value="">RS</optin>
        <optin value="">RO</optin>
        <optin value="">RR</optin>
        <optin value="">SC</optin>
        <optin value="">SP</optin>
        <optin value="">SE</optin>
        <optin value="">TO</optin>
      </select>
    </div>
  </form>
</template>

<style scoped>
.title {
  margin: auto;
  text-align: center;
  color: rgb(124, 124, 206);
}
</style>
