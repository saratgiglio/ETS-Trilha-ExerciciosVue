 
<template>
  <div>
    <input type="number" v-model.number="celsius" placeholder="Graus Celsius" />
    <p>Fahrenheit: {{ fahrenheit }}</p>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue';

const celsius = ref(0);

const fahrenheit = computed(() => (celsius.value * 9/5) + 32);
</script>
