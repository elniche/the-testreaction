<template>

  <div class="todo" v-if="master" @click="pararTimer"> 
      Let's Play
  </div>
  
</template>

<script>
export default {
props: ["delays"],

data() {
  return {
    master: false,
    tiempo: null,
    reacionar: 0
  }
},

methods: {
  //ESTA FUNCION ES LLAMADA CUANDO EL AZUL ESTA EN LA PANTALLA
  comensarTimer() {
 this.tiempo = setInterval(() => {
       this.reacionar += 10;
 }, 10)
  },
  pararTimer() {
clearInterval(this.tiempo);
this.$emit('end', this.reacionar)  
  }
},

mounted() {
  setTimeout(() => {
    this.master = true;
    this.comensarTimer();
  }, this.delays)

  }
}
</script>

<style>
.todo {
    width: 300px;
    border-radius: 20px;
    background: blue;
    color: wheat;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>