<script setup>
import { onBeforeUnmount, onUnmounted } from "vue";

onBeforeUnmount(() => {
    console.log("onBeforeUnmount - Componente está prestes a ser Desmontado");
});

onUnmounted(() => {
    console.log("onUnmounted - Componente desmontado");
});
</script>

<template>
    <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. In neque
        laborum odit voluptate et magnam nobis unde eos! Dolores doloremque,
        quis natus quibusdam enim at distinctio accusantium dolorem assumenda
        sit.
    </p>
</template>
