<template>
    <div class="calculator">
      <input type="number" v-model="valor1" @input="calcular" placeholder="0" />
      <div class="operacoes">
        <button class="operacao-btn somar" :class="{ ativo: calculo === 'somar' }" @click="selecionarOperacao('somar')">+</button>
        <button class="operacao-btn subtrair" :class="{ ativo: calculo === 'subtrair' }" @click="selecionarOperacao('subtrair')">-</button>
        <button class="operacao-btn multiplicar" :class="{ ativo: calculo === 'multiplicar' }" @click="selecionarOperacao('multiplicar')">x</button>
        <button class="operacao-btn dividir" :class="{ ativo: calculo === 'dividir' }" @click="selecionarOperacao('dividir')">/</button>
      </div>
      <input type="number" v-model="valor2" @input="calcular" placeholder="0" />
      <div class="resultado flex justify-center items-center h-48 bg-gray-100 border border-gray-300 p-4 rounded">
      Resultado: {{ resultado }}
    </div>
    </div>
  </template>
  
  <script setup>
  import { reactive, ref } from 'vue';
  
  const valor1 = ref('');
  const valor2 = ref('');
  const calculo = ref(null);
  const resultado = ref(0);
  
  function calcular() {
    const v1 = parseFloat(valor1.value);
    const v2 = parseFloat(valor2.value);
    if (!isNaN(v1) && !isNaN(v2) && calculo.value !== null) {
      switch (calculo.value) {
        case 'somar':
          resultado.value = v1 + v2;
          break;
        case 'subtrair':
          resultado.value = v1 - v2;
          break;
        case 'multiplicar':
          resultado.value = v1 * v2;
          break;
        case 'dividir':
          resultado.value = v2 === 0 ? "Undefined" : v1 / v2;
          break;
      }
    } else {
      resultado.value = 0; // Reiniciar resultado se algum valor não for um número ou nenhum cálculo foi selecionado
    }
  }
  
  function selecionarOperacao(op) {
    calculo.value = op;
  }
  </script>
  
  <style scoped>
  .calculator {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    flex-direction: column;
  }
  
  .calculator input, .resultado {
    text-align: center;
    font-size: 5.9em;
    padding: 10px;
    margin-bottom: 10px;
  }
  
  .operacoes {
    padding-top: 20px;
    padding-bottom: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }
  
  .operacao-btn {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: white;
    border: 2px solid black;
    padding: 10px;
    font-size: 1.9em;
    cursor: pointer;
    transition: background-color 0.3s, color 0.3s;
  }
  
  .operacao-btn.ativo {
    background-color: blue;
    color: white;
  }
</style>
