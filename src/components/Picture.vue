<template>
  <img v-bind:src="avatar" v-bind:alt="descricao">
  <MudarImagem @mudar-imagem="trocarImagem"/>
</template>

<script>

  import MudarImagem from './MudarImagem.vue'

  export default {
    name: 'Picture',
    components:{
      MudarImagem
    },
    data() {
      return {
        avatar: '/img/avatar.png',
        descricao: 'Imagem do avatar'
      }
    },
    methods: {
      trocarImagem() {
        this.avatar = '/img/avatar2.png'
      }
    }
  }
</script>