<template>
  <div id="app" class="font-serif">
    <Header />
    <Motivation />
    <Concern />
    <Solution />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Motivation from "./components/Motivation.vue";
import Concern from "./components/Concern.vue";
import Solution from "./components/Solution.vue";

export default {
  name: "App",
  components: {
    Header,
    Motivation,
    Concern,
    Solution
  }
};
</script>

<style>
</style>
