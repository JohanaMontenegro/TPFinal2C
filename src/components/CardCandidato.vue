<template>
  <div class="card">
    <img v-bind:src="candidato.avatar" alt="avatar">
    <h3 class="name">{{candidato.name}}</h3>
    <h2 class="surname">{{candidato.surname}}</h2>
    <p class="age"> Edad: {{candidato.age}}</p>
    <p class="searchType">Busqueda: {{candidato.searchType}}</p>
    <p class="skills"> Habilidades: {{candidato.skill}}</p>
    <p class="movility" v-if="candidato.movility">Movilidad: Si</p>
    <p class="movility" v-else>Movilidad: No</p>
    <p class="workingHours" v-if="candidato.workingHours">Horario Full-Time</p>
    <p class="workingHours" v-else>Horario Half-Time</p>
    <p class="link"> <a v-bind:href=candidato.link>Linkedin</a></p>
    <p class="linkCv"> <a v-bind:href=candidato.linkCv>Link CV</a></p>

  </div>
</template>
<script>
export default {
  name: 'CardCandidato',
  props: ["candidato"]
}

</script>

<style>
.card {
  display: flex;
  flex-flow: column;
  justify-content: center;
  width: 380px;
  height: 450;
  min-height: 300px;
  background: rgb(245, 248, 248);
  overflow: auto;
  padding: 10px 15px;
  margin-bottom: 24px;
  margin-right: 10px;
  margin-left: 10px;
  cursor: pointer;
  color: rgb(2, 2, 2);
  transform: scale(1.01);
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2),
    0 0px 1px 0 rgba(0, 0, 0, 0.19);
  border: 1px solid rgb(189, 189, 189);
}

img {
  width: auto;
  height: auto;
  margin: 5px;
  margin-bottom: 10px;
}

.card h3,
h2,
p {
  margin: 0px
}

.card h2 {
  margin-bottom: 10px;
  color: rgb(36, 36, 36);
}

.card h3 {
  font-weight: 300;
  color: rgb(58, 58, 58);
}

.card p {
  margin-bottom: 4px;
}

.link {
  margin-top: 5px;
}

.card a{
  text-decoration: none;
  color: inherit;
  color:black;
}

.card a:hover{
  cursor: pointer;
  text-decoration: underline;
}
</style>