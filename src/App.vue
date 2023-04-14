<template>
  <div>
    <Header v-bind:esta_logado="true" />
    <PrimeiroComponente />
    <p class="paragrafo-pai">O dado de App é {{ testando  }}</p>
    <LifeCycle />
    <Pessoa />
  </div>
</template>

<script>
  import PrimeiroComponente from './components/PrimeiroComponente.vue';
  import LifeCycle from './components/LifeCycle.vue'
  import Pessoa from './components/Pessoa.vue'
  import Header from './components/Header.vue'

  export default {
    name: 'App',
    components: {
      PrimeiroComponente,
      LifeCycle,
      Pessoa,
      Header
    },
    data() {
      return {
        testando: 'Teste'
      }
    }
  }
</script>

<style>
  body {
    background-color: #333;
    color: #fff;
  }

  a {
    color: #ff0000;
  }

  .paragrafo-pai {
    background-color: #ff0000;
  }
</style>