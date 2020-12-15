<template>
    <div id= "borrar">
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
    name: "borrar",
    data:function(){
        return{
            informacion : "En este componte se borra toda la informacion de un  hotel!",
            mensaje : ""
        }
    }, 
    methods:{ 
        created:function(){
            let self = this
            let nombre_hotel = null
            let aux = "https://prueba-sprin3-back.herokuapp.com/hotel/delete/"
            nombre_hotel = document.getElementsByName("nombreHotel")[0].value
            let url = aux+nombre_hotel
            axios.delete(url)
            .then((result) =>{
                self.mensaje = result.data
            })
            .catch((error)=> {
                self.mensaje = "[EL REGISTRO NO SE PUEDE BORRAR, NO EXISTE EN LA BASE DE DATOS]"
            });
        }
    }
}
</script>

<style>
    #borrar input{
        display:block;
        display: flex;
        padding: 0%;
        margin-left: 50px;
    }

    #borrar button{
        margin-left: 50px;
        margin-top: 20px;
    }
</style>