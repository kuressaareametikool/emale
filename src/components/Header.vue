<template>
  <section id="header-section" class="w-screen h-full bg-yellow-dark font-sans text-brown relative">
    <div id="header-background-pattern"></div>
    <div class="container">
      <div id="header-background-flower"></div>
      <div id="header-background-leaves">
        <img src="../assets/header-background-leaves.svg" alt="Flowers" />
      </div>
      <main class="relative z-10 lg:flex lg:h-full lg:items-center">
        <div class="lg:flex lg:flex-row">
          <!-- Header content left -->
          <div class="mx-auto py-32 flex flex-col lg:py-0 lg:w-1/2 lg:pt-12">
            <h1
              class="mb-8 font-serif text-4xl text-center sm:text-5xl lg:text-left"
            >Emadelt emadele</h1>
            <p
              class="mb-8 mx-auto opacity-75 text-center tracking-wide leading-6 sm:max-w-lg sm:text-xl sm:leading-8 lg:text-left lg:w-full"
            >Meie eesmärk on rääkida emade jaoks olulistest teemadest ning algatada ühiskondlikke arutelusid ning olulisi muudatusi, et muuta emade elukorraldust Eestis paremaks.</p>
            <div class="mx-auto flex flex-col-reverse sm:flex-row lg:mx-0">
              <SmoothScroll
                class="mb-8 sm:mr-8 bg-white py-4 rounded-lg shadow-lg text-center px-10 cursor-pointer hover:shadow-none"
                href="#footer-section"
              >Räägi oma lugu</SmoothScroll>
              <SmoothScroll
                class="mb-8 bg-white py-4 rounded-lg shadow-lg text-center px-10 cursor-pointer hover:shadow-none"
                href="#calculator-section"
              >Kalkulaator</SmoothScroll>
            </div>
            <div class="mx-auto text-center lg:mx-0 lg:text-left">
              <p class="text-xs opacity-50 flex max-w-xs lg:max-w-none">
                <span class="mr-2">
                  <img
                    class="hidden h-3 pt-1 lg:block"
                    src="../assets/star-icon.svg"
                    alt="Star of Life icon"
                  />
                </span>Kirjuta sulle olulisest teemast, mis vajab käsitlemist või jutusta oma lugu.
              </p>
            </div>
          </div>
          <!-- Header content right -->
          <div class="hidden lg:block">
            <img src="../assets/header-content-image.svg" alt="Header Main image" />
          </div>
          <div></div>
        </div>
      </main>
    </div>
    <div id="header-section-divider"></div>
  </section>
</template>

<script>
import SmoothScroll from "./SmoothScroll.vue";
export default {
  components: {
    SmoothScroll
  }
};
</script>

<style scoped>
.container {
  width: 90%;
  height: 100%;
  max-width: 1088px;
  margin: auto;
  position: relative;
}

#header-background-pattern {
  position: absolute;
  width: 100%;
  height: 100%;
  background-image: url(../assets/header-background-pattern.svg);
  background-repeat: repeat;
  z-index: 0;
  opacity: 0.5;
}

#header-background-flower {
  position: absolute;
  height: 400px;
  width: 450px;
  bottom: 0;
  left: -12rem;
  background-image: url("../assets/header-background-flower.svg");
  background-repeat: no-repeat;
  background-position: bottom left;
  background-size: cover;
  opacity: 0.6;
}

#header-background-leaves {
  position: absolute;
  bottom: 1rem;
  right: -1rem;
}

#header-section-divider {
  position: absolute;
  bottom: -1px;
  z-index: 10;
  width: 100%;
  height: 25px;
  background-image: url(../assets/header-section-divider.png);
  background-repeat: repeat-x;
}

@media screen and (min-width: 640px) {
  #header-background-flower {
    left: -3rem;
    height: 330px;
    width: 380px;
  }
}

@media screen and (min-width: 1024px) {
  #header-section {
    height: 100vh;
  }
  #header-background-flower {
    opacity: 1;
    height: 170px;
    width: 200px;
    left: 9rem;
  }
}
</style>
