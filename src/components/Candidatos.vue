<template>
  <div id="Candidatos-container">
    <CardCandidato v-for="candidato in candidatos" :key="candidato.id" :candidato="candidato" :class="candidato-card"></CardCandidato>
    <div class="createCard" @click="clickCard(id)">
    </div>
  </div>
</template>
  
<script>
import CardCandidato from "./CardCandidato.vue"

export default {
  name: 'CandidatosComponent',
  props: {
    msg: String
  },
  components: { CardCandidato },

  data() {
    return { candidatos: [] }
  },

  created() {
    fetch("https://6350867b3e9fa1244e4813ff.mockapi.io/candidatos/v1/candidatos")
      .then((response) => response.json())
      .then((persona) => {
        this.candidatos = persona
        console.log(this.candidatos)
      });
  }
}


</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#Candidatos-container{
  display: flex;
  flex-wrap: wrap;
  padding-left: 20px;
  padding-top: 25px;
}

.card{
  max-width: 200px;
}


ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>