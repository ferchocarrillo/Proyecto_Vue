<template>
    <div class="div">
        <h2>Lista de tareas</h2>
        <input type="text" name="" id="" v-model="nuevaTarea" @keyup.enter="addTarea">
        <ul>
            <li v-for="(tarea, index) in tareas" :key="index">{{tarea}}</li>
            <button @click="borrarTarea">Borrar tarea</button>
        </ul>
    </div>
</template>
<script setup>

import {ref} from 'vue';
const tareas = ref([]);
const nuevaTarea = ref('');
const addTarea = () => {
    tareas.value.push(nuevaTarea.value);
    nuevaTarea.value = '';
}


const borrarTarea = (index) => {
    tareas.value.splice(index,1);
}


</script>
<style scoped>

</style>