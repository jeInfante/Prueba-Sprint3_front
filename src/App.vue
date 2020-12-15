<template>
  <div id="app">
    <img src="./assets/logo_test.png" alt="" width="5%" height="5%" />
    <div class= 'encabezado'>
      <header>
          <h1>{{titulo}}</h1>
          <nav>
            <button v-on:click="init">Inicio</button>
            <button v-on:click="verificacion">Verificación</button>
            <button v-on:click="buscar">Buscar</button>
            <button v-on:click="actualizar">Actualizar</button>
            <button v-on:click="crear">Crear</button>
            <button v-on:click="borrar">Borrar</button>
          </nav>
      </header>
    </div>
    <div class ="main-component">
      <router-view>
      </router-view>
    </div>
    <div class ="footer">
      <h2>{{piePagina}}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data: function(){
    return{
      titulo : 'AT HOME: Pronóstico de Hoteles',
      piePagina : 'AT HOME: Pronóstico de Hoteles',
    }
  },
  methods:{
    init: function(){
      this.$router.push({name:"test"})
    },
    verificacion: function(){
      this.$router.push({name:"verificacion"})
    },
    buscar: function(){
      this.$router.push({name:"buscar"})
    },
    actualizar: function(){
      this.$router.push({name:"actualizar"})
    },
    borrar: function(){
      this.$router.push({name:"borrar"})
    },
    crear: function(){
      this.$router.push({name:"crear"})
    }
  }
}
</script>

<style>
#body {
  margin-top: 0 0 0 0;
}

.header {
    margin: 0%;
    padding: 0;
    width: 100%;
    height: 10vh;
    min-height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
.encabezado h1 {
    font-family: Times, "Times New Roman", serif;
    font-style: bold;
    color: #E5E7E9;
    margin: 0%;
    background-color: #283747;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    
}

.encabezado nav {
    display: flex;
    align-items: center;
    font-size: 20px;
}
.encabezado nav button{
    color: #E5E7E9;
    background: #133396;
    border: 1px solid #E5E7E9;
    border-radius: 5px;
    padding: 10px 20px;
}
.encabezado nav button:hover{
    color: #283747;
    background: #E5E7E9;
    border: 1px solid #E5E7E9;
}

.main-component{
    font-family: Times, "Times New Roman", serif;
    height: 60vh;
    margin: 0%;
    padding: 0%;
    background: #FDFEFE;
    color: #133396
}

.footer{
    margin: 0;
    padding: 0;
    width: 100%;
    height: 15vh;
    background-color: #283747;
    color: #E5E7E9;
}

.footer h2{
    font-family: Times, "Times New Roman", serif;
    font-style: italic;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

</style>
