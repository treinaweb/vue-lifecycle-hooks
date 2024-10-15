<script setup>
import { ref, onMounted, onBeforeMount, onUpdated, onBeforeUpdate } from "vue";

const mensagem = ref("");
const contador = ref(0);

function incrementar() {
    contador.value++;
}

// Quando for montado
onMounted(() => {
    mensagem.value = "Componente Montado";
    console.log("onMounted executado");
});

// Antes de ser montado
onBeforeMount(() => {
    console.log("onBeforeMount executado!");
});

// Quando for atualizado
onUpdated(() => {
    console.log("onUpdate executado");
});

// Antes de ser atualizado
onBeforeUpdate(() => {
    console.log("onBeforeUpdate executado");
});
</script>

<template>
    <h1>{{ mensagem }}</h1>
    <h2>{{ contador }}</h2>
    <button @click="incrementar">Adicionar</button>
</template>
