<template>
  <div id="app" class="p-4">
    <h1>Investment Calculator</h1>
    <InvestmentCalculator />
  </div>
</template>

<script>
import InvestmentCalculator from "./components/InvestmentCalculator.vue";

export default {
  name: "App",
  components: {
    InvestmentCalculator,
  },
};
</script>

<style>
#app {
  text-align: center;
  font-family: Arial, sans-serif;
  background-color: #f9fafb;
  padding: 20px;
}
h1 {
  color: #333;
}
</style>
