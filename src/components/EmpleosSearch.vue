<template>
    <div id="ESDivContainer">

        <p>Filtrar por:</p>
        <ul>Full-Time</ul>
        <li>Si</li>
        <li>No</li>

        <ul>Rubro</ul>
        <li>Rubro 1</li>
        <li>Rubro 2</li>


    </div>


</template>
    
<script>
export default {
    name: 'EmpleosSearchComponent',
    props: {

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
    