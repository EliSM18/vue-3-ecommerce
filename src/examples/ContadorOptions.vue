<script lang="ts">
    export default {
        data() {
            return {
                count: 0
            };
        },
        methods: {
            increase() {
                this.count++;
            },
            decrease() {
                this.count--;
            }
        }, mounted() {
            console.log('Componente Contador montado' + this.count);
        }
    }
</script>

<template>
    <p>Objetivo: Tienes que llegar a 10 click</p>
    <h1> Contador: {{ count }} </h1>
    <button @click="increase">Incrementar</button>
    <button @click="decrease">Decrementar</button>
    <p v-if="count < 10">¡Vamos tú puedes!</p>
    <p v-else>¡Lo lograste!</p>
</template>