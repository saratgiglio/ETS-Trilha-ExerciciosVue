 <template>
  <div>
    <h1>{{ mensagem }}</h1>
    <button @click="reverterMensagem">Reverse Message</button>
    <button @click="acrescentarExclamacao">Append !</button>
    <button @click.prevent="botaoPrevent">Prevent Default Button</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const mensagem = ref('Hello World');

function reverterMensagem() {
  mensagem.value = mensagem.value.split('').reverse().join('');
}

function acrescentarExclamacao() {
  mensagem.value += '!';
}

function botaoPrevent() {
  alert('Botão com preventDefault clicado!');
}
</script>
