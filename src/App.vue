<template>
  <div id="app" class="font-serif">
    <Header />
    <Motivation />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Motivation from "./components/Motivation.vue";

export default {
  name: "App",
  components: {
    Header,
    Motivation
  }
};
</script>

<style>
</style>
