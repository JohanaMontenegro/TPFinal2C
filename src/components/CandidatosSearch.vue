<template>
    <div id="CSDivContainer">

        <p>Busqueda por:</p>
        <input id="SName" type="text" placeholder="Nombre" />
        <input id="SApellido" type="text" placeholder="Apellido" />

        <p>Filtrar por:</p>
        <ul>Edad</ul>
        <li>18 - 30</li>
        <li>30 - 40</li>
        <li>40 - 50</li>
        <li>50 - 99</li>

        <ul>Full-Time</ul>
        <li>Si</li>
        <li>No</li>
        
        <ul>Movilidad</ul>
        <li>Si</li>
        <li>No</li>

    </div>

</template>
    
<script>
export default {
    name: 'CandidatosSearchComponent',
    props: {

    }
}
</script>
    
<style scoped>

#CSDivContainer {
    background-color: rgb(226, 226, 226);
    max-width: 200px;
    min-width: 200px;
    padding-left: 30px;
    padding-top: 20px;
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

#SName {
    margin-top:8px;
}
</style>
    