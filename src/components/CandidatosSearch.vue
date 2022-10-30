<template>
    <div id="CSDivContainer">

        <p>Busqueda por:</p>
        <input id="SName" type="text" placeholder="Nombre" v-model="sBName" v-on:input="this.$emit('searchByName', this.sBName)"/>
        <input id="SApellido" type="text" placeholder="Apellido" v-model="sBSName" v-on:input="this.$emit('searchBySurname', this.sBSName)"/>

        <p>Filtrar por:</p>
        <ul>Edad</ul>
        <li v-on:click="this.$emit('searchByAge',{y1:18,y2:30})">18 - 30</li>
        <li v-on:click="this.$emit('searchByAge',{y1:30,y2:40})">30 - 40</li>
        <li v-on:click="this.$emit('searchByAge',{y1:40,y2:50})">40 - 50</li>
        <li v-on:click="this.$emit('searchByAge',{y1:50,y2:99})">50 - 99</li>

        <ul>Full-Time</ul>
        <li v-on:click="this.$emit('searchByFullTime',true)">Si</li>
        <li v-on:click="this.$emit('searchByFullTime',false)">No</li>

        <ul>Movilidad</ul>
        <li v-on:click="this.$emit('searchByMovility',true)">Si</li>
        <li v-on:click="this.$emit('searchByMovility',false)">No</li>

        <p v-if="resetCBtn" v-on:click="this.$emit('restartSearch')" id="p-restart-cSearch">Reestablecer</p>
    </div>

</template>
    
<script>


export default {
    name: 'CandidatosSearchComponent',
    props: {
        resetCBtn: Boolean,
    }, data() {
        return {
            sBName: '',
            sBSName: '',
        }
    },
    methods: {
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
    color: grey;
}

li:hover {
    cursor: pointer;
    text-decoration: underline;
}

input {
    max-width: 170px;
    border: none;
    border-radius: 20px;
    padding: 5px;
    background-color: white;
    margin-bottom: 10px;
}

#SName {
    margin-top: 8px;
}

#p-restart-cSearch {
    color: grey;
}

#p-restart-cSearch:hover {
    color: rgb(135, 135, 135);
    cursor: pointer;
    text-decoration: underline;
}

</style>
    