<template>
  <div>
    <h1>Olá Vue</h1>
    <p>Meu nome é {{ name }} e trabalho como {{ profissão }}</p>
    <MultiplosEventos />
  </div>
</template>

<script>
  import MultiplosEventos from './MultiplosEventos.vue'

  export default {
    name: 'PrimeiroComponente',
    components: {
      MultiplosEventos
    },
    data() {
      return {
        name: 'Leonardo',
        profissão: 'Programador'
      }
    }
  }
</script>