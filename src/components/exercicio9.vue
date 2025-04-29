<template>
  <div>
    <div style="background-color: lightgray; width: 100%; height: 30px;">
      <div :style="{ backgroundColor: 'blue', width: progresso + '%', height: '100%' }"></div>
    </div>

    <input type="range" v-model="duracao" min="1" max="100" />
    <button @click="reiniciar">Reiniciar</button>
  </div>
</template>

<script setup>
import { ref, watch, onMounted, onUnmounted } from 'vue';

const progresso = ref(0);
const duracao = ref(10);
let intervalo = null;

watch(duracao, () => {
  reiniciar();
});

function iniciarContagem() {
  intervalo = setInterval(() => {
    if (progresso.value < 100) {
      progresso.value += 100 / duracao.value;
    } else {
      clearInterval(intervalo);
    }
  }, 1000);
}

function reiniciar() {
  clearInterval(intervalo);
  progresso.value = 0;
  iniciarContagem();
}

onMounted(() => {
  iniciarContagem();
});

onUnmounted(() => {
  clearInterval(intervalo);
});
</script>

