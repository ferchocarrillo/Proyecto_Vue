<template>
    <div class="sidebar">

        <h2>Barra Lateral</h2>

        <ul>
            <li><router-link to="/Contador">Contador</router-link></li>
            <li><router-link to="/ListaDeTareas">Lista de tareas</router-link></li>
            <li><router-link to="/SelectMultiple">Selector</router-link></li>
            <li><router-link to="/registrar">Registrar</router-link></li>
        </ul>



    </div>
</template>

<script setup>
</script>

<style scope>
.sidebar {
    width: 200px;
    background-color: #f0f0f0;
    padding: 20px;
}
</style>