<template>
<!-- 4:49 netifly hosting tut-->
   <h1> Let's Test Your Reaction </h1>  
   <button @click="Comienza" :disabled="this.jugando"> Touch!!  </button>
   <Elbloke v-if="this.jugando" :delays="delays"    @end="Evdiencia"/>
   <Resultado v-if="this.ensena" :score="score" />

   
</template>

<script>
import Elbloke from './components/Elbloke.vue'
import Resultado from './components/Resultado.vue'

export default {
  name: 'App',
  components: {
    Elbloke,Resultado
  },

  data() {
    return {
     jugando: false,
     delays: '',
     score: null,
     ensena: false
    }
  },
  methods: {
    ///delays before another blocke appears on the screen and keeping track if a user is currently playing
    Comienza() {
      this.jugando = true;
      this.delays = 2000 + Math.random() * 5000;
      this.ensena = false;
      
    },

    Evdiencia(reactivo) {
       this.score = reactivo
       this.jugando = false;
       this.ensena = true;
    }
  }
}
</script>

<style>

body {
  background-color: gray;
}

h1 {
  color:black;
  font-family: cursive;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
