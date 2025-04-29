 
<template>
  <div>
    <p @mouseover="mostrarTexto">Paire o mouse sobre mim</p>
    <p v-if="textoAparece">Texto apareceu dinamicamente!</p>

    <p :style="{ color: corTextoPreto }" @click="mudarParaVermelho">Clique aqui para mudar para vermelho</p>
    
    <p :style="{ color: corTextoAzul }" @click="alternarAzulVerde">Clique aqui para alternar azul/verde</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const textoAparece = ref(false);
const corTextoPreto = ref('black');
const corTextoAzul = ref('blue');

function mostrarTexto() {
  textoAparece.value = true;
}

function mudarParaVermelho() {
  corTextoPreto.value = 'red';
}

function alternarAzulVerde() {
  corTextoAzul.value = corTextoAzul.value === 'blue' ? 'green' : 'blue';
}
</script>
