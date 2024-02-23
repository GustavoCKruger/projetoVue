<script setup>
import { ref, onMounted } from 'vue'

const contador = ref(0)

function incrementarContador() {
  contador.value++
}

function decrementarContador() {
  contador.value--
}

function moverBotao() {
    const botao = document.getElementById("meuBotao");
    const novaPosicaoX = Math.random() * (window.innerWidth - botao.offsetWidth);
    const novaPosicaoY = Math.random() * (window.innerHeight - botao.offsetHeight);
    botao.style.left = novaPosicaoX + "px";
    botao.style.top = novaPosicaoY + "px";
    contador.value = 0;
}

onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})


</script>

<template>
  <p>{{ contador }}</p>
  <div class="row">
    <button @click="incrementarContador">+</button>
  <button @click="decrementarContador">-</button>
  <button id="meuBotao" @click="moverBotao">Limpar</button>
  </div>
</template>

<style scoped>
  .row{
    display: flex;
    align-items: center;
    align-self: center;
  }
  button{
    height: 50px;
    width: 100px;
    margin: 0 10px 0 10px;
    background-color: darkslateblue;
    border: none;
  }
</style>