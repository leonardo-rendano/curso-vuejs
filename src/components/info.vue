<template>
  <div>
    <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
    <p v-else>Estou em busca de novas oportunidades</p>
    <p>Utilizo as seguintes tecnologias para backend:</p>
    <ul>
      <li v-for="(technology, index) in backend_technologies" v-bind:key="index">
        {{ technology }}
      </li>
    </ul>
    <p>Utilizo as seguintes tecnologias para Frontend:</p>
    <ul>
      <li v-for="technology in frontend_technologies" v-bind:key="technology.id">
        {{ technology.language }}
      </li>
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
        textoBotaoEmail: 'Mostrar email',
        backend_technologies: [
          'Javascript',
          'PHP',
          'Python',
          'java'
        ],
        frontend_technologies: [
          { id: 1, language: 'HTML' },
          { id: 2, language: 'CSS' },
          { id: 3, language: 'Vue' }
        ]
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