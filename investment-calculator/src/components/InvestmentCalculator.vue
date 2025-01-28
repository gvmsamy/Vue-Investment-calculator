<template>
  <div class="calculator">
    <form @submit.prevent="calculateFutureValue">
      <div class="form-group">
        <label for="principal">Principal Amount ($):</label>
        <input
          type="number"
          id="principal"
          v-model.number="principal"
          placeholder="Enter principal amount"
          required
        />
      </div>
      <div class="form-group">
        <label for="rate">Annual Interest Rate (%):</label>
        <input
          type="number"
          id="rate"
          v-model.number="rate"
          placeholder="Enter interest rate"
          required
        />
      </div>
      <div class="form-group">
        <label for="years">Years:</label>
        <input
          type="number"
          id="years"
          v-model.number="years"
          placeholder="Enter number of years"
          required
        />
      </div>
      <button type="submit">Calculate</button>
    </form>

    <div v-if="futureValue !== null" class="result">
      <h3>Future Value:</h3>
      <p>${{ futureValue.toFixed(2) }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      principal: 0,
      rate: 0,
      years: 0,
      futureValue: null,
    };
  },
  methods: {
    calculateFutureValue() {
      const rateDecimal = this.rate / 100;
      this.futureValue =
        this.principal * Math.pow(1 + rateDecimal, this.years);
    },
  },
};
</script>

<style>
.calculator {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
h3 {
  color: #4caf50;
}
.form-group {
  margin-bottom: 15px;
}
label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}
input {
  width: 100%;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 4px;
}
button:hover {
  background-color: #45a049;
}
.result {
  margin-top: 20px;
  font-size: 1.2em;
  color: #333;
}
</style>
