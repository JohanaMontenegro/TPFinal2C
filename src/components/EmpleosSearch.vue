<template>
    <div id="ESDivContainer">



        <p>Filtrar por:</p>
        <ul>Carga Horaria:</ul>
        <li>Full-Time</li>
        <li>Part-Time</li>

        <ul>Rubro:</ul>
        <li v-for="empleo in empleosrubros" :key="empleo.id" >{{ empleo }}</li>


    </div>


</template>
    
<script>
export default {
    name: 'EmpleosSearchComponent',
    props: {

    },
    data() {
    return { empleos:[],
        empleosft: [],
        empleospt: [],
        empleosrubros:[]
    }
    },
    methods: {

        empleosFullTime(){
            this.empleos.forEach(empleo => {
                if (empleo.workinghours === "Full-Time"){
                    this.empleosft.push(empleo);
                }
                
            });
            console.log("Empleos Full-Time")
            console.log(this.empleosft)
        },
        empleosPartTime(){
            this.empleos.forEach(empleo => {
                if (empleo.workinghours === "Part-Time"){
                    this.empleospt.push(empleo);
                }
                
            });
            console.log("Empleos Part-Time")
            console.log(this.empleospt)
        },
        empleosAllRubros(){
            this.empleos.forEach(empleo => {
                this.empleosrubros.push(empleo.item)
            });
            console.log("Empleos Rubros")
            console.log(this.empleosrubros)
        }


    },

    async created() {
        fetch("https://6351b70e9d64d7c71307422e.mockapi.io/empleos/empleos")
        .then((response) => response.json())
        .then((trabajo) => {
            this.empleos = trabajo
            this.empleosFullTime();
            this.empleosPartTime();
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

</style>
    