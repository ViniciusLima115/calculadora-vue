<!-- Calculadora.vue -->

<template>
    <div class="calculator">
      <div class="card">
        <div class="card-body">
          <h2 class="card-title text-center mb-4">Calculadora Aritmética</h2>
          <div class="form-group">
            <label for="num1">Número 1:</label>
            <input v-model="num1" type="number" class="form-control" @input="calcularResultado" />
          </div>
          <div class="form-group">
            <label for="num2">Número 2:</label>
            <input v-model="num2" type="number" class="form-control" @input="calcularResultado" />
          </div>
          <div class="form-group">
            <label for="operacao">Operação:</label>
            <select v-model="operacao" class="form-control" @change="calcularResultado"> 
              <option value="+">Soma</option>
              <option value="-">Subtração</option>
              <option value="*">Multiplicação</option>
              <option value="/">Divisão</option>
            </select>
          </div>
          <div class="form-group">
            <label for="resultado">Resultado:</label>
            <input :value="resultado" type="text" class="form-control resultado" disabled />
          </div>
          
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        num1: 0,
        num2: 0,
        operacao: '+',
      };
    },
    computed: {
      resultado() {
        switch (this.operacao) {
          case '+':
            return this.num1 + this.num2;
          case '-':
            return this.num1 - this.num2;
          case '*':
            return this.num1 * this.num2;
          case '/':
            return this.num1 / this.num2;
          default:
            return 0;
        }
      },
    },
    methods: {
      clearFields() {
        this.num1 = 0;
        this.num2 = 0;
        this.operacao = '+';
      },
      calcularResultado() {
        // You can keep your existing logic for calculating the result here
      },
    },
  };
  </script>
  
  <style scoped>
  .calculator {
    text-align: center;
    margin-top: 50px;
  }
  
  .card {
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 1024px;
    margin: 0 auto;
    background-color: lightgray;
  }
  
  .card-title {
    color: #000000;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  input,
  select,
  button {
    margin-top: 10px;
    width: 100%;
    background-color: grey;
    text-align: center;
  }
  .resultado{
    color: white;
    background-color: black;
    text-align: center;
  }

  </style>
  