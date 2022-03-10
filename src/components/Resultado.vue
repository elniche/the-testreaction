<template>
<p class="pico"> Your reaction time is: {{ this.score }} ms....... </p>
<p class="rango">{{this.rank}} </p>
</template>


<script>

export default {
    props: ["score"],

    data() {
        return {
            rank: null
        }
    },

    mounted() {
      if(this.score < 250 ) {
          this.rank = "Wow,,YOu have quick reactions!!";
      } else if( this.score > 250) {
          this.rank = "Not Bad!!!!";
      } else if (this.score > 300) {
          this.rank = "Keep Training... YOu will get better....."
      }
    }
}


</script>


<style>
.pico {
  color:black;
}

.rango {
    font-family: fantasy;
    font-size: 600%;
}

</style>