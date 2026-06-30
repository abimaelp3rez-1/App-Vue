<template>
    <div id="contenedor-app">
        <h1>Panel de control</h1>

        <section id="btnOpciones" class="botonera">
            <button
                v-for="boton in acciones"
                :key="boton.id"
                :class="['btn', `btn-${boton.clase}`]"
                @click="ejecutarAccion(boton.evento)"
            >
                {{ boton.texto }}
            </button>
        </section>

        <!-- El Pop-up vive aquí en el template y escucha a la variable -->
        <PopUp :is-open="isPopUpVisible" @close="isPopUpVisible = false" />
    </div>
</template>

<script setup>
import { ref } from 'vue'
import PopUp from './popUp.vue'; // Verifica que la ruta y mayúsculas sean correctas

const isPopUpVisible = ref(false);

const acciones = [
    {id: 1, texto: 'Nuevo', evento: 'nuevo', clase: 'primario'},
    {id: 2, texto: 'Desplegar', evento: 'desplegar', clase: 'secundario'},
    {id: 3, texto: 'Editar', evento: 'editar', clase: 'alerta'},
    {id: 4, texto: 'Eliminar', evento: 'eliminar', clase: 'peligro'},
]

const ejecutarAccion = (evento) => {
    if (evento === 'nuevo') {
        // Cambiamos la variable a true y el template abre el PopUp
        isPopUpVisible.value = true;
    } else {
        alert(`Hiciste click en el boton: ${evento}`)
    }
}
</script>

<style scoped>
.botonera{
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.btn{
    padding: 10px 20px;
    border: none;
    border-radius: 20px;
    cursor: pointer;
    font-size: 14px;
}

.btn:hover{
    opacity: 0.8;
    color: white;
    background-color: black;
}
</style>
