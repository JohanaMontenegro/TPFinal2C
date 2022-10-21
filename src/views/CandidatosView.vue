<template>
  <div id="CDivContainer">
    <CandidatosSearchComponent />
    <CandidatosComponent />
  </div>
</template>



<script>
import CandidatosComponent from "../components/Candidatos.vue";
import CandidatosSearchComponent from "../components/CandidatosSearch.vue";

export default {
  name: "CandiComponent",
  components: {
    CandidatosComponent,
    CandidatosSearchComponent
  },
}

</script>

<style scoped>

#CDivContainer {
  margin: 0;
  display: flex;
  flex-direction: row;
  height: 100%;
}

</style>