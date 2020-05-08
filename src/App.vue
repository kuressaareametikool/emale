<template>
  <div id="app" class="font-serif">
    <Navigation />
    <Header />
    <Motivation />
    <Concern />
    <Solution />
    <Calculator />
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue";
import Header from "./components/Header.vue";
import Motivation from "./components/Motivation.vue";
import Concern from "./components/Concern.vue";
import Solution from "./components/Solution.vue";
import Calculator from "./components/Calculator.vue"

export default {
  name: "App",
  components: {
    Navigation,
    Header,
    Motivation,
    Concern,
    Solution,
    Calculator
  }
};
</script>

<style>
</style>
