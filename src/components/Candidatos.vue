<template>


  <CandidatosSearchComponent @searchByName="searchByName($event)" @searchBySurname="searchBySurname($event)"
  @searchByAge="searchByAge($event)" @searchByFullTime="searchByFullTime($event)" 
  @searchByMovility="searchByMovility($event)" @restartSearch="restartSearch($event)" 
  :resetCBtn=this.resetCBtn ></CandidatosSearchComponent>

  <div  id="Candidatos-container">
    <CardCandidato v-for="candidato in listFiltered" :key="candidato.id" :candidato="candidato">
    </CardCandidato>
    <div class="createCard" @click="clickCard(id)">
    </div>
  </div>


</template>
  
<script>
import CardCandidato from "./CardCandidato.vue";
import CandidatosSearchComponent from "./CandidatosSearch.vue";

export default {
  name: 'CandidatosComponent',
  props: {
    msg: String
  },
  components: {
    CardCandidato,
    CandidatosSearchComponent
  },

  data() {
    return {
      list: [],
      listFiltered: [],
      resetCBtn: false,
    }
  },
  methods: {
    async loadAPI() {
      return fetch("https://6350867b3e9fa1244e4813ff.mockapi.io/candidatos/v1/candidatos")
        .then((response) => response.json())
        .then((persona) => {
          this.list = persona;
          this.listFiltered = this.list;
        });
    },
    searchByName(nameS) {
      this.resetCBtn = true;

      nameS = nameS.toLowerCase();
      this.listFiltered = [];
      this.list.forEach(candidato => {
        if((candidato.name.toLowerCase()).startsWith(nameS, 0)){
          this.listFiltered.push(candidato)
        }

      });

    },

    searchBySurname(surnameS) {
      this.resetCBtn = true;

      surnameS = surnameS.toLowerCase();
      this.listFiltered = []

      this.list.forEach(candidato => {
        if((candidato.surname.toLowerCase()).startsWith(surnameS, 0)){
          this.listFiltered.push(candidato)
        }

      });
    },

    searchByAge(data) {
      this.resetCBtn = true;

      this.listFiltered = []
      this.list.forEach(candidato => {
        if(Number(candidato.age) >= data.y1 && Number(candidato.age) <= data.y2){
          this.listFiltered.push(candidato)
        }

      });
    },

    searchByFullTime(boolean) {
      this.resetCBtn = true;

      this.listFiltered = []
      this.list.forEach(candidato => {
        if(candidato.workingHours === boolean){
          this.listFiltered.push(candidato)
        }

      });
    },

    searchByMovility(boolean) {
      this.resetCBtn = true;

      this.listFiltered = []
      this.list.forEach(candidato => {
        if(candidato.movility=== boolean){
          this.listFiltered.push(candidato)
        }

      });
    },
    
    restartSearch(){
      this.listFiltered = this.list;
      this.resetCBtn = false;
    }

  }
  ,

  created() {
    this.loadAPI();
    
  },
}


</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#Candidatos-container {
  display: flex;
  flex-wrap: wrap;
  padding-left: 20px;
  padding-top: 25px;
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

/* CARD CANDIDATOS */
</style>