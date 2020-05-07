<template>
  <section
    id="navigation-section"
    class="mt-4 font-sans font-light text-brown absolute w-full top-0 h-20 z-50"
  >
    <div class="container">
      <div class="flex items-center justify-between">
        <div>
          <a href="/">
            <img src="../assets/emale-logo.svg" alt="MTÜ Emale logo" />
          </a>
        </div>
        <div>
          <ul class="flex">
            <li class="uppercase hover:opacity-50 text-base font-medium">
              <ScrollLink href="#motivation-section">Meist</ScrollLink>
            </li>
            <li class="uppercase ml-6 hover:opacity-50 text-base font-medium">
              <ScrollLink href="#">Kalkulaator</ScrollLink>
            </li>
            <li class="uppercase ml-6 hover:opacity-50 text-base font-medium">
              <ScrollLink href="#">Kontakt</ScrollLink>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ScrollLink from "../components/ScrollLink.vue";
export default {
  components: {
    ScrollLink
  }
};
</script>

<style scoped>
.container {
  width: 90%;
  max-width: 1088px;
  margin: auto;
  height: 100%;
}
</style>
