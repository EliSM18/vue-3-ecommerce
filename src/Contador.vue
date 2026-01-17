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
        },
        mounted() {
            console.log('Componente Contador montado'+ this.count);
        }
    }
</script>

<template>
    <div style="text-align: center; margin-top: 40px; align-self: center;">
        <h1>Contador: {{ count }}</h1>
        <button @click="increase">Incrementar</button>
        <button @click="decrease">Decrementar</button>
    </div>
</template>