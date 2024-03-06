<template>
  <header class="p-5 mb-4 mt-4 bg-light rounded-3">
    <h1 class="text-center">Calculadora</h1>
  </header>
  <div id="app" class="container">
    <div class="row">
      <div class="col-md-4">
        <input type="number" class="form-control" v-model.number="num1" @input="calcular">
      </div>
      <div class="col-md-4">
        <select class="form-control" v-model="operacao" @change="calcular">
          <option value="somar">+</option>
          <option value="subtrair">-</option>
          <option value="multiplicar">*</option>
          <option value="dividir">/</option>
        </select>
      </div>
      <div class="col-md-4">
        <input type="number" class="form-control" v-model.number="num2" @input="calcular">
      </div>
    </div>
    <p class="mt-3">Resultado {{ resultado }} </p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: 'somar',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case 'somar':
          this.resultado = this.num1 + this.num2;
          break;
        case 'subtrair':
          this.resultado = this.num1 - this.num2;
          break;
        case 'multiplicar':
          this.resultado = this.num1 * this.num2;
          break;
        case 'dividir':
          this.resultado = this.num1 / this.num2;
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>

<style>
</style>
