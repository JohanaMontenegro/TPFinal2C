<template>
  <div class="home">
    <div id="main-container">
      <div id="HomeHeader">
        <div>
          <h2>Bienvenido al area de empleo</h2>
          <p>En esta sección podras encontrar diversas opciones, tanto para buscar como para ofrecer empleo</p>
        </div>
        <div>
          <img src="./img/bolsaTrabajo.jpg" alt="">
        </div>
      </div>
      <div id="HomeSections" >
        <div id="Empleador" class="hSections">
          <h3>Sos Empleador?</h3>
          <p>Postula tu oferta laboral haciendo click en el botón</p>
          <button>Postulá tu oferta</button>
        </div>
        <div id="Empleado" class="hSections">
          <h3>Buscas trabajo?</h3>
          <p>Carga tus datos y habilidades haciendo click en el botón</p>
          <button > <a href="candidatos"> Cargá tus datos </a></button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'HomeView',
  components: {
  }
}
</script>

<style scoped>
#main-container {
    font-family: 'Inter', sans-serif;
}

#main-container h2,h3 {
    font-family: 'Viga', sans-serif;
    
}
#main-container h3 {
    font-size: 25px;
}

#main-container div {
    background-color: white;

}

#HomeHeader {
    min-width: 700px;
    max-width: 800px;
    margin: auto;
    margin-top: 20px;
    border: 1px solid rgb(173, 173, 173);
    box-shadow: 0px 0px 4px 2px rgba(0, 0, 0, 0.2);
    display: flex;
    flex-direction: row;
    text-align: center;
}

#HomeHeader img {
    max-width: 260px;
    margin-top: 10px;
    margin-left: 10px;
}

#HomeHeader h2{
  margin-top:30px;
  margin-bottom: 20px;
}

#HomeHeader p{
    padding-left: 30px;
    padding-right: 30px;

}


#HomeSections {
    min-width: 700px;
    max-width: 800px;
    margin: auto;
    margin-top: 10px;
    display: flex;
    justify-content: space-between;
    padding-top: 10px;
}

.hSections {
    max-width: 360px;
    margin: 0px;
    border: 1px solid rgb(173, 173, 173);
    box-shadow: 0px 0px 4px 2px rgba(0, 0, 0, 0.2);
    text-align: center;
    padding-bottom: 20px;
    padding-left: 10px;
    padding-right: 20px;
    background-color: rgb(243, 18, 18);
}

.hSections p{
  padding-left: 9px;
  padding-right: 9px;
}

.hSections button {
    background-color: #005977;
    color: white;
    padding: 9px;
    border: none;
    border-radius: 5px;
}

.hSections button:hover {
    cursor: pointer;
}

a{
  text-decoration: none; 
  color:inherit
}
</style>
