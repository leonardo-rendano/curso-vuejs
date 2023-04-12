<template>
  <div>
    <h2>Esta é a descrição da pessoa: {{ nome }}</h2>
    <Info />
    <Form />
  </div>
</template>

<script>
  import Info from './info.vue'
  import Form from './form/Form.vue'

  export default {
    name: 'Pessoa',
    components: {
      Info,
      Form
    },
    data() {
      return {
        nome: 'Leonardo'
      }
    },
  }
</script>