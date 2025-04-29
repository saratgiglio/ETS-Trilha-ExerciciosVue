 
<template>
  <div>
    <select v-model="tipoVoo">
      <option value="ida-e-volta">Voo com regresso</option>
      <option value="só-ida">Voo só de ida</option>
    </select>

    <div v-if="tipoVoo === 'só-ida'">
      <input type="date" v-model="dataIda" />
    </div>

    <div v-else>
      <input type="date" v-model="dataIda" />
      <input type="date" v-model="dataVolta" />
    </div>

    <button @click="marcarViagem">Marcar</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const tipoVoo = ref('só-ida');
const dataIda = ref('');
const dataVolta = ref('');

function marcarViagem() {
  if (tipoVoo.value === 'só-ida') {
    alert(`Voo de ida partindo em ${dataIda.value}`);
  } else {
    alert(`Voo de ida em ${dataIda.value} e regressando em ${dataVolta.value}`);
  }
}
</script>
