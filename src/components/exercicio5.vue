 
<template>
  <div>
    <button @click="alternarLista">Alternar Lista</button>
    <button @click="empurrarNumero">Empurrar Número</button>
    <button @click="largarNumero">Largar Número</button>
    <button @click="inverterLista">Inverter Lista</button>

    <ul v-if="mostrar">
      <li v-for="numero in lista" :key="numero">{{ numero }}</li>
    </ul>
    <p v-else>A lista não está vazia, mas está escondida</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const lista = ref([1, 2, 3]);
const mostrar = ref(true);

function alternarLista() {
  mostrar.value = !mostrar.value;
}

function empurrarNumero() {
  lista.value.push(lista.value.length + 1);
}

function largarNumero() {
  lista.value.pop();
}

function inverterLista() {
  lista.value.reverse();
}
</script>
