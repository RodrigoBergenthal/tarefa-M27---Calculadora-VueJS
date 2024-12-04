<template>
  <div class="container">
    <Cabecalho />
    <main>
      <Calculadora :estado="estado" @input-valor1="getValor1" @input-valor2="getValor2" @change-operador="getOperador"/>
    </main>
    <Rodape />
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue';
import Rodape from './components/Rodape.vue';

const estado = reactive({
  valor1: '',
  valor2: '',
  resultado: 0,
  calculo: 'somar', // Inicialmente, a operação é somar
})

function getValor1(event) {
  estado.valor1 = event.target.value;
}

function getValor2(event) {
  estado.valor2 = event.target.value;
}

function getOperador(event) {
  // Desativar todos os botões antes de ativar o novo
  document.querySelectorAll('.operacao-btn').forEach(btn => btn.disabled = true);
  event.target.classList.add('ativo');
  estado.calculo = event.target.value;
}

const calcular = () => {
  const v1 = parseFloat(estado.valor1);
  const v2 = parseFloat(estado.valor2);
  switch (estado.calculo) {
    case 'subtrair':
      estado.resultado = v1 - v2;
      break;
    case 'somar':
      estado.resultado = v1 + v2;
      break;
    case 'dividir':
      estado.resultado = v2 === 0 ? "Undefined" : v1 / v2;
      break;
    case 'multiplicar':
      estado.resultado = v1 * v2;
      break;
    default:
      estado.resultado = 0;
  }
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header, footer {
  flex: none; /* Não crescem nem encolhem */
}

main {
  flex: 1; /* Ocupa o espaço restante */
  display: flex;
  justify-content: center;
  align-items: center;
}

.operacao-btn {
  margin: 0 5px;
  padding: 10px 20px;
  font-size: 1em;
  cursor: pointer;
  border: none;
  background-color: #f8f9fa;
  color: #333;
}

.operacao-btn.ativo {
  background-color: #007bff;
  color: white;
}
</style>
