<script setup>
import { ref, onMounted, onBeforeMount } from "vue";

const mensagem = ref("");

onMounted(() => {
    mensagem.value = "Componente Montado";
    console.log("onMounted executado");
});

onBeforeMount(() => {
    console.log("onBeforeMount executado!");
});
</script>

<template>
    <h1>{{ mensagem }}</h1>
</template>
