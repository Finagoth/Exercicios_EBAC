<template>
  <div class="container">
    <h1>Calculadora Aritmética</h1>

    <input
      type="number"
      v-model.number="numero1"
      placeholder="Primeiro número"
    />

    <select v-model="operacao">
      <option value="+">Soma</option>
      <option value="-">Subtração</option>
      <option value="*">Multiplicação</option>
      <option value="/">Divisão</option>
    </select>

    <input
      type="number"
      v-model.number="numero2"
      placeholder="Segundo número"
    />

    <p><strong>Resultado:</strong> {{ resultado }}</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+'
    }
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.numero1 + this.numero2
        case '-':
          return this.numero1 - this.numero2
        case '*':
          return this.numero1 * this.numero2
        case '/':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro'
        default:
          return 0
      }
    }
  }
}
</script>

<style>
.container {
  max-width: 400px;
  margin: 40px auto;
  text-align: center;
}

input,
select {
  width: 100%;
  margin: 10px 0;
  padding: 8px;
}
</style>
