<template>
  <div id="EDivContainer">
    <EmpleosComponent />
  </div>
</template>
  
<script>
import EmpleosComponent from "../components/Empleos.vue";

export default {
  name: "EmplComponent",
  components: {
    EmpleosComponent
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