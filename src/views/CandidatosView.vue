<template>
  <div id="CDivContainer">
    <CandidatosComponent />
  </div>
</template>



<script>
import CandidatosComponent from "../components/Candidatos.vue";

export default {
  name: "CandiComponent",
  components: {
    CandidatosComponent
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