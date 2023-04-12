<template>
  <div>
    <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
    <p v-else>Estou em busca de novas oportunidades</p>
    <p>Utilizo as seguintes tecnologias:</p>
    <ul>
      <li>Javascript</li>
      <li>PHP</li>
      <li>Python</li>
    </ul>
    <div>
      <button @click="showEmail">{{ textoBotaoEmail }}</button>
    </div>
    <p v-show="mostrar_email">Mande uma mensagem para: {{ email }}</p>
    <div>
      <button @click="showLink">{{ textoBotao }}</button>
    </div>
    <p v-show="mostrar_link">Para acessar meu portfolio basta  <a v-bind:href="meu_link" target="_blank">clicar aqui</a></p>
    <Picture />
  </div>
</template>

<script>
  import Picture from './Picture.vue'

  export default {
    name: 'Info',
    components: {
      Picture
    },
    data() {
      return {
        esta_trabalhando: true,
        mostrar_email: false,
        email: 'leonardo.rendano@email.com',
        meu_link: 'https:google.com',
        mostrar_link: false,
        textoBotao: 'Mostrar link do portfolio',
        textoBotaoEmail: 'Mostrar email'
      }
    },
    methods: {
      showEmail() {
        if (!this.mostrar_email) {
          this.textoBotaoEmail = 'Ocultar email'
        } else {
          this.textoBotaoEmail = 'Mostrar email'
        }
        this.mostrar_email = !this.mostrar_email
      },
      showLink() {
        if (!this.mostrar_link) {
          this.textoBotao = 'Ocultar link do portfolio'
        } else {
          this.textoBotao = 'Mostrar link do portfolio'
        }
        this.mostrar_link = !this.mostrar_link
      }
    }
  }
</script>