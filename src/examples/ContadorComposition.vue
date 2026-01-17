<script setup lang="ts">
    import { onMounted, ref } from 'vue';
    const contador = ref(0);
    function increase() {
        contador.value++;
    }
    onMounted( function() {
        console.log('El valor inicial del contador es: ', contador.value);
    });
</script>
<template>
    <p> Hola soy la versión con Composition API</p>
    <h1>{{ contador }}</h1>
    <button @click="increase">Incrementar</button>
</template>