<template>
  <div id="app" class="font-serif">
    <Header />
    <Motivation />
    <Concern />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Motivation from "./components/Motivation.vue";
import Concern from "./components/Concern.vue";

export default {
  name: "App",
  components: {
    Header,
    Motivation,
    Concern
  }
};
</script>

<style>
</style>
