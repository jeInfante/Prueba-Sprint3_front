<template>
    <div id= "verificacion">
        <header>
          <h2>{{informacion}}</h2>
        </header>
        <input type="text" name="nombreHotel"/>
        <button v-on:click="created">EJECUTAR</button>
        <p>{{mensaje}}</p>
    </div> 
</template>

<script>
import axios from 'axios'; 
export default {
    name: "verificacion",
    data:function(){
        return{
            informacion : "En este componte se verifica si el hotel existe!",
            mensaje : ""
        }
    },
    methods:{       
    created:function(){
        let nombre_hotel = null
        nombre_hotel = document.getElementsByName("nombreHotel")[0].value
        let self = this
        let post = {
        nombre: nombre_hotel ,
        };
        axios.post("https://prueba-sprin3-back.herokuapp.com/hotel/verification/",post)
            .then((result) =>{
                self.mensaje = result.data
            })
            .catch((error)=> {
                self.mensaje = "[EL REGISTRO NO EXISTE EN LA BASE DE DATOS]"
            });
        }
    }
}
</script>

<style>
    #verificacion input{
        display:block;
        display: flex;
        padding: 0%;
        margin-left: 50px;
    }

    #verificacion button{
        margin-left: 50px;
        margin-top: 20px;
    }
</style>
