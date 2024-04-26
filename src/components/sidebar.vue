<template>
    <div class="sidebar">

        <h2>Bienvenido</h2>
        <h3>Nombre: {{ nombre }}</h3>
        <h3>Email: {{ email }}</h3>

        <ul>
            <li><router-link to="/Contador">Contador</router-link></li>
            <li><router-link to="/ListaDeTareas">Lista de tareas</router-link></li>
            <li><router-link to="/SelectMultiple">Selector</router-link></li>
            <li><router-link to="/registrar">Registrar</router-link></li>
        </ul>



    </div>
</template>

<script setup>

import { useRegistrarStore } from '@/modules/registro/stores/registrarStore';
const registrarStore = useRegistrarStore();
import { ref, watch } from 'vue';
const nombre = ref(registrarStore.nombre.value);
const email = ref(registrarStore.email.value);
watch(() => registrarStore.nombre, (newValue) =>{
    nombre.value = newValue;
});
watch(() => registrarStore.email, (newValue) =>{
    email.value = newValue;
});


</script>

<style scope>
.sidebar {
    width: 200px;
    background-color: #f0f0f0;
    padding: 20px;
}
</style>