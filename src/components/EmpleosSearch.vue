<template>
    <div id="ESDivContainer">
        <p>Filtrar por:</p>
        <ul>Carga Horaria:</ul>
        <li v-on:click="this.$emit('searchByFT',true)" >Full-Time</li>
        <li v-on:click="this.$emit('searchByFT',false)" >Part-Time</li>

        <ul>Rubro:</ul>
        <li v-for="empleo in empleosrubros" :key="empleo.id" 
        v-on:click="this.$emit('searchByRubro', empleo)">{{ empleo }}</li>

        <p v-if="resetEBtn" v-on:click="this.$emit('restartSearch')" id="p-restart-eSearch">Reestablecer </p>
    </div>
</template>
    
<script>
export default {
    name: 'EmpleosSearchComponent',
    props: {
        resetEBtn: Boolean,
    },
    data() {
    return { empleos:[],
        empleosrubros:[]
    }
    },
    methods: {
        empleosAllRubros(){
            this.empleos.forEach(empleo => {
                this.empleosrubros.push(empleo.item)
            });
        }
    },

    async created() {
        fetch("https://6351b70e9d64d7c71307422e.mockapi.io/empleos/empleos")
        .then((response) => response.json())
        .then((trabajo) => {
            this.empleos = trabajo
            this.empleosAllRubros();
        });
    }
}

</script>
    
<style scoped>

#ESDivContainer {
    background-color: rgb(226, 226, 226);
    max-width: 200px;
    min-width: 200px;
    padding-left: 30px;
}

ul,
li,
input {
    list-style-type: none;
    list-style: none;
}

ul {
   padding-left: 0px;
   margin-bottom: 5px;
   font-weight: bold;
}

li {
    padding-left: 15px;
    color:grey;
}

li:hover {
    cursor: pointer;
    text-decoration: underline;
}

input {
    max-width:170px;
    border: none;
    border-radius: 20px;
    padding: 5px;
    background-color: white;
    margin-bottom: 10px;
}

#p-restart-eSearch {
    color: grey;
}

#p-restart-eSearch:hover {
    color: rgb(135, 135, 135);
    cursor: pointer;
    text-decoration: underline;
}


</style>
    