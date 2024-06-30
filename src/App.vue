<template>
  <h1>{{ title }}</h1>
  <hr>
  <div v-if="showModal">
    <ModalComponent :entete='entete' :text='text' @close="toogleMoadal">
      <template v-slot:liens>
        <a href="#">Signup now</a>
        <a href="#">More...</a>
      </template>
    </ModalComponent>
  </div>
  <button @click="toogleMoadal" class="bouton">Ouvrir le modal</button>
</template>

<script>

import ModalComponent from './components/MadalComponent.vue'

export default {
  name: 'App',
  components:{
    ModalComponent
  },
  data(){
    return{
      title : 'Bienvenu dans mon première application vue JS',
      entete : 'Pré-inscrivez vous maintenant',
      text : 'Allez dans fpros.fr et entrez votre nom et email',
      showModal: false,
    }
  },
  methods:{
    toogleMoadal(){
      this.showModal = !this.showModal
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  font-size: 4rem;
}
.bouton{
  position: fixed;
}
a{
  border: 1px solid black;
  border-radius: 5px;
  padding: 10px 15px;
  text-decoration: none;
  margin: 0 30px;
}
a:hover{
  background: #111;
  color: #fff;
}
</style>
