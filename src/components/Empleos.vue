<template>
  <div id="Empleos-container">
  <EmpleosCard v-for="empleo in empleos" :key="empleo.id" :empleo="empleo"></EmpleosCard>
</div>
</template>

<script>
import EmpleosCard from "./EmpleosCard.vue"
export default {
  name: 'EmpleosComponent',
  props: {
    msg: String
  },
  components: { EmpleosCard },

  data() {
    return { empleos:[] }
  },

  created() {
    fetch("https://6351b70e9d64d7c71307422e.mockapi.io/empleos/empleos")
      .then((response) => response.json())
      .then((trabajo) => {
        this.empleos = trabajo
        console.log(this.empleos)
      });
  }
}
</script>

<style>

#Empleos-container{

  display:flex;
  flex-wrap: wrap;
  padding-top: 30px;
  padding-left: 30px;

}

</style>
