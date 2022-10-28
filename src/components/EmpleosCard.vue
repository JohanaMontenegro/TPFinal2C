<template>
    <div class="ecard">
        <img v-bind:src="empleo.avatar" alt="avatar">
        <h2 class="name">{{empleo.name}}</h2>
        <h3 class="eitem"> Rubro: {{empleo.item}}</h3>
        <p class="description"> Descripción del puesto: {{empleo.description}}</p>
        <p class="workinghours"> Carga Horaria: {{empleo.workinghours}}</p>
        <p class="requirement"> Requisitos: {{empleo.requirement}}</p>
        <div class="ebuttons">
            <button @click="CargarCv"> Cargar CV</button>
            <button @click="EnviarCv"> Enviar CV</button>
        </div>
    </div>
</template>
<script>
export default {
    name: 'EmpleosCard',
    props: ["empleo"],
}
</script>

<style>

</style>