<template>
  <div id="app" class="container mt-5">
    <Titulo>Calculadora Aritmética</Titulo>
    <Entradas :id="'numero1'" :label="'Número 1'" :valor="numero1" @atualizar="atualizarNumero1"></Entradas>
    <Entradas :id="'numero2'" :label="'Número 2'" :valor="numero2" @atualizar="atualizarNumero2"></Entradas>
    <div class="col-md-4">
      <label for="operacao">Operação:</label>
      <select v-model="operacao" class="form-control" @change="calcular">
        <option value="+">Soma</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
    </div>
    <Resultado :resultado="resultado"></Resultado>
  </div>
</template>

<script>
import Titulo from './components/Titulo.vue';
import Entradas from './components/Entradas.vue';
import Resultado from './components/Resultado.vue';

export default {
  components: {
    Titulo,
    Entradas,
    Resultado,
  },
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: "+",
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case "+": return this.numero1 + this.numero2;
        case "-": return this.numero1 - this.numero2;
        case "*": return this.numero1 * this.numero2;
        case "/": return this.numero1 / this.numero2;
        default: return 0;
      }
    },
  },
  methods: {
    atualizarNumero1(valor) {
      this.numero1 = parseFloat(valor);
      this.calcular();
    },
    atualizarNumero2(valor) {
      this.numero2 = parseFloat(valor); 
      this.calcular();
    },
    calcular() {
 
    },
  },
};
</script>

<style>

</style>
