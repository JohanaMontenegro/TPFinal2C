<template>
  <div id="main-app-container">

    <!-- HEADER content -->
    <div id="header-container">
      <div id="header">
        <h1 id="pag-name">Bolsa de Trabajo</h1>
        <nav>
          <router-link to="/">INICIO</router-link> |
          <router-link to="/empleos">EMPLEOS</router-link> |
          <router-link to="/candidatos">CANDIDATOS</router-link>
        </nav>
      </div>
    </div>

    <!-- ROUTER VIEW -->
    <div id="div-routerview">
      <router-view />
    </div>
    <!-- FOOTER content -->
    <div id="footer">
      <div id="footer-text">
        <p>Bolsa de empleo Madariaga 2022</p>
        <p>Proyecto de estudio</p>
      </div>
    </div>

  </div>
</template>

<script>


export default {
  name: "App",
  components: {

  },
}

</script>


<style>

/* PAGE FORMAT */

body {
  height: 100%;
  margin: 0;
}

#main-app-container {
  display: flex;
  flex-flow: column;
  height: 100%;
}

#header-container{
  flex: 0 1 auto;
}

#div-routerview {
  flex: 1 1 auto;
}

#app {
  height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#main-app-container {
  display: flex;
  flex-flow: column;
  height: 100%;
}

/* HEADER */

#header-container {
  background-color: #06799F;
  box-shadow: 0px 0px 5px 3px rgba(0, 0, 0, 0.2);
}

#pag-name {
  color: white;
  margin-left: 9px;
  margin-right: 9px;
}

#header {
  display: flex;
  flex-direction: row;
  min-width: 600px;
  max-width: 800px;
  margin: auto;
  justify-content: space-between;
}

/* NAV BAR */

nav {
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255, 255, 255, 0.252);

}

nav a {
  font-weight: bold;
  color: #f6f6f6d1;
  margin: 5px;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: rgb(255, 255, 255);
}

/* FOOTER */

#footer p{
  font-size: small;
  margin:5px;
}
#footer-text {
  margin-top: 10px
}

#footer {
  flex: 0 1 60px;
  background-color: rgb(142, 142, 142);
  text-align: center;
}


</style>
