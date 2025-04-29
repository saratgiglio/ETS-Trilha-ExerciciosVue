 
<template>
  <div>
    <button @click="contar">Contador: {{ contador }}</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const contador = ref(0);

function contar() {
  contador.value++;
}
</script>
