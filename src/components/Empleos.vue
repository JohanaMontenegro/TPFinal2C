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
    return { empleos: [] }
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
#Empleos-container {

  display: flex;
  flex-wrap: wrap;
  padding-top: 30px;
  padding-left: 30px;

}

/* CARD EMPLEOS */

.ecard {
  display: flex;
  flex-flow: column;
  justify-content: center;
  max-width: 270px;
  min-width: 230px;
  background: rgb(245, 248, 248);
  overflow: auto;
  padding: 10px 15px;
  margin-bottom: 24px;
  margin-right: 10px;
  cursor: pointer;
  color: rgb(2, 2, 2);
  box-shadow: 0 1px 5px 0 rgba(0, 0, 0, 0.19);
  border: 1px solid rgb(179, 179, 179);
}

.ecard img {
  max-width: 220px;
  margin: auto;
}

.eitem {
  font-size: 16px;
  font-weight: 600;
}

.ecard button {
  padding: 10px;
  font-weight: 600;
  font-size: 13px;
  color: rgb(255, 255, 255);
  background-color: hsl(216, 57%, 24%);
  border-radius: 6px;
  border: 1px solid black;
  width: 100px;
}

.ecard button:hover {
  background-color: hsl(216, 52%, 34%);
  cursor: pointer;
}

.ebuttons {
  margin-top: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 10px;
}

.ecard p {
  margin: 0px;
  margin-top: 5px;
  margin-bottom: 10px;
}

.ecard h2 {
  margin-bottom: 0px;
}
</style>
