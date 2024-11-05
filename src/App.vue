<script setup>
import { ref, onMounted, onBeforeMount, onUpdated, onBeforeUpdate } from "vue";
import Texto from "./components/Texto.vue";

const mensagem = ref("");
const contador = ref(0);
const showComponent = ref(true);
const items = ref([]);

const fetchData = async () => {
    try {
        const response = await fetch("../public/data/nomes.json");
        const data = await response.json();
        items.value = data;
    } catch (error) {
        console.error("O erro é: ", error);
    }
};

function toggleComponent() {
    showComponent.value = !showComponent.value;
}

function incrementar() {
    contador.value++;
}

// Quando for montado
onMounted(() => {
    mensagem.value = "Componente Montado";
    console.log("onMounted executado");
    fetchData();
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
    <br />
    <button @click="toggleComponent">Mostrar/Esconder</button>
    <Texto v-if="showComponent" />

    <div v-if="items.length === 0">Carregando...</div>
    <ul v-else>
        <li v-for="item in items" :key="item.id">{{ item.name }}</li>
    </ul>
</template>
