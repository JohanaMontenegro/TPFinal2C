<template>
    <div class="card">
        <img v-bind:src="empleo.avatar" alt="avatar">
        <h2 class="name">{{empleo.name}}</h2>
        <h3 class="item"> Rubro: {{empleo.item}}</h3>
        <p class="description"> Descripción del puesto: {{empleo.description}}</p>
        <p class="workinghours"> Carga Horaria: {{empleo.workinghours}}</p>
        <p class="requirement"> Requisitos: {{empleo.requirement}}</p>
        <div class="buttons">
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
.card {
    display: flex;
    flex-flow: column;
    justify-content: center;
    width: 270px;
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

.card img {
    max-width: 220px;
    margin: auto;
}

.item {
    font-size: 16px;
    font-weight: 600;
}

.card button {
    padding: 10px;
    font-weight: 600;
    font-size: 15px;
    color: black;
    background-color: hsl(180, 20%, 99%);
    border-radius: 6px;
    border: 2px solid black;
    width: 100px;
}

.buttons{
    margin-top: 10px;
    display: flex;
    flex-direction: row;
    justify-content:space-between ;
    padding: 10px;
}

.card p {
    margin: 0px;
    margin-top: 5px;
    margin-bottom: 10px;
}

.card h2 {
    margin-bottom: 0px;
}

.card button:hover{
    background-color: rgb(203, 208, 233);
    cursor: pointer;
}

</style>