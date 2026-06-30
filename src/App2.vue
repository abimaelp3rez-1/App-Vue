<script setup>
import { ref } from 'vue';

const colorActual = ref('blue')

const cambiarColor = () =>{
    colorActual.value = 'red'
} 

const color2 = "color: blue"
const nombre = "Juan"

const frutas = ["pera", "manzana", "platano"]


</script>

<template>

    <section>
        <h1 style=" color: coral;">Hola soy Juan</h1>
        <h2 v-bind:style="{color: colorActual}">Azul</h2>
        <button v-on:click="cambiarColor">Cambiar color</button>
        <h1>Hola mi nombre es {{ nombre.toUpperCase() }}</h1>
        <h1 :style="color2">Azul</h1>
    </section>
    
    
    
</template>



<style scoped>

</style>