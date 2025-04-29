<template>
  <div>
    <input v-model="texto" placeholder="Digite algo" />
    <span>{{ texto }}</span>

    <br><br>

    <input type="checkbox" v-model="verificado" /> Verificado: {{ verificado }}

    <br><br>

    <div>
      <label><input type="checkbox" value="Sara" v-model="nomesSelecionados" /> Sara</label>
      <label><input type="checkbox" value="João" v-model="nomesSelecionados" /> João</label>
      <label><input type="checkbox" value="Marcos" v-model="nomesSelecionados" /> Marcos</label>
    </div>
    <p>Nomes verificados: {{ nomesSelecionados.join(', ') }}</p>

    <br>

    <div>
      <label><input type="radio" value="Radio Um" v-model="radioSelecionado" /> Radio Um</label>
      <label><input type="radio" value="Radio Dois" v-model="radioSelecionado" /> Radio Dois</label>
    </div>
    <p>Escolhido: {{ radioSelecionado }}</p>

    <br>

    <div>
      <select v-model="selecionado">
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <p>Selecionado: {{ selecionado }}</p>
    </div>

    <br>

    <div>
      <select multiple v-model="selecionadosMultiplos">
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <p>Selecionados: {{ selecionadosMultiplos.join(', ') }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const texto = ref('');
const verificado = ref(false);
const nomesSelecionados = ref([]);
const radioSelecionado = ref('');
const selecionado = ref('');
const selecionadosMultiplos = ref([]);
</script>
