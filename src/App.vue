<script setup>
import { ref, onMounted } from 'vue'

const contador = ref(0)

function incrementarContador() {
  contador.value++
}

function decrementarContador() {
  if(contador.value > 0){
    contador.value--;
  }
}

function limpar(){
  contador.value = 0;
}


onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})


</script>

<template>
  <button id="num" disabled>{{ contador }}</button>
  <div id="options">
    <button id="adicionar" @click="incrementarContador">Incrementar</button>
    <button id="decrementar" @click="decrementarContador">Decrementar</button>
    <button id="limpar" @click="limpar">Limpar</button>
  </div>
</template>

<style scoped>
  #num{
    color: black;
    background-color: azure;
  }
  button{
    background-color: blueviolet;
    border-radius: 20px;
  }
  .options{
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>