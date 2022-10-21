<template>
  <div id="EDivContainer">
    <EmpleosSearchComponent />
    <EmpleosComponent />
  </div>
</template>
  
<script>
import EmpleosComponent from "../components/Empleos.vue";
import EmpleosSearchComponent from "../components/EmpleosSearch.vue";

export default {
  name: "EmplComponent",
  components: {
    EmpleosComponent,
    EmpleosSearchComponent
  },
}

</script>

<style scoped>
#EDivContainer {
  margin: 0;
  display: flex;
  flex-direction: row;
  height: 100%;
}
</style>