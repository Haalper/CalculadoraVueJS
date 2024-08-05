<template>
  <div class="calculator">
    <input type="number" v-model.number="num1" @input="calculate" class="input-field">
    <select v-model="operator" @change="calculate" class="operator-select">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model.number="num2" @input="calculate" class="input-field">
    <div class="result">
      Resultado: {{ result }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = this.num1 + this.num2;
          break;
        case '-':
          this.result = this.num1 - this.num2;
          break;
        case '*':
          this.result = this.num1 * this.num2;
          break;
        case '/':
          this.result = this.num1 / this.num2;
          break;
        default:
          this.result = 0;
      }
    }
  }
};
</script>

<style scoped>
.calculator {
  max-width: 300px;
  margin: 50px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.input-field {
  width: calc(50% - 22px);
  padding: 8px;
  margin: 10px;
  font-size: 16px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.operator-select {
  padding: 8px;
  margin: 10px;
  font-size: 16px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.result {
  font-size: 18px;
  font-weight: bold;
  margin-top: 20px;
}
</style>
