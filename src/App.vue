<script setup>
import { reactive } from 'vue';

const estado = reactive({
  numero1: 0,
  numero2: 0,
  resultado: 0,
});

function somar() {
  estado.resultado = estado.numero1 + estado.numero2;
}

function subtrair() {
  estado.resultado = estado.numero1 - estado.numero2;
}

function multiplicar() {
  estado.resultado = estado.numero1 * estado.numero2;
}

function dividir() {
  if (estado.numero2 === 0) {
    return;
  }
  estado.resultado = estado.numero1 / estado.numero2;
}
</script>

<template>
  <div class="calculator-container">
    <div class="container">
      <div class="inputs">
        <input v-model.number="estado.numero1" type="number" placeholder="Número 1" />
        <input v-model.number="estado.numero2" type="number" placeholder="Número 2" />
      </div>
      <div class="operations">
        <button @click="somar" type="button">+</button>
        <button @click="subtrair" type="button">-</button>
        <button @click="multiplicar" type="button">*</button>
        <button @click="dividir" type="button">/</button>
      </div>
      <div class="result">
        <p>Resultado: {{ estado.resultado }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.calculator-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background-image: url('./assets/wallpaper.avif');
  background-size: cover;
  background-position: center;
}

.container {
  border-radius: 15px;
  background-color: rgba(255, 255, 255, 0.8);
  padding: 80px;
}

.inputs {
  margin-bottom: 30px;
  display: flex;
  flex-direction: column; 
  row-gap: 10px;
}

.operations {
  text-align: center;
}

.operations button {
  margin: 5px;
  font-size: 18px;
  padding: 5px 10px;
  background-color: #2ecc71;
  color: #fff;
  border: none;
  border-radius: 30%;
  cursor: pointer;
}
.result {
  margin-top: 10px;
  padding: 10px;
  color: black;
}
</style>

