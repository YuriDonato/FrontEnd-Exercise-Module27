<script setup>
import { ref, computed } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('+');

const resultado = computed(() => {
  switch (operacao.value) {
    case '+':
      return numero1.value + numero2.value;
    case '-':
      return numero1.value - numero2.value;
    case '*':
      return numero1.value * numero2.value;
    case '/':
      return numero1.value / numero2.value;
    default:
      return 0;
  }
});
</script>

<template>
  <center>
    <div class="container mt-5 bg-dark-subtle rounded-5">
      <h1 class="mb-4 pt-4">Calculadora Aritmética</h1>
      <div class="row">
        <div class="col-md-4">
          <div class="form-group">
            <label for="numero1">Número 1</label>
            <input type="number" v-model="numero1" class="form-control">
          </div>
        </div>

        <div class="col-md-4">
          <div class="form-group">
            <label for="numero2">Número 2</label>
            <input type="number" v-model="numero2" class="form-control">
          </div>
        </div>
        <div class="col-md-4">
          <div class="form-group">
            <label for="operacao">Operação</label>
            <select v-model="operacao" class="form-control">
              <option value="+">Adição</option>
              <option value="-">Subtração</option>
              <option value="*">Multiplicação</option>
              <option value="/">Divisão</option>
            </select>
          </div>
        </div>
      </div>
      <div class="row mt-3 pb-4">
        <div class="col-md-12">
          <h3>Resultado: {{ resultado }}</h3>
        </div>
      </div>
    </div>
  </center>
</template>

<style scoped></style>
