<template>
  <section
    id="footer-section"
    class="mt-16 w-screen h-full bg-yellow-dark font-sans text-brown relative"
  >
    <div id="footer-background-pattern"></div>
    <div id="footer-divider"></div>
    <div class="container">
      <div class="pt-24 mb-12">
        <h1 class="font-serif text-center text-xl">Kirjuta meile!</h1>
      </div>
      <div class="flex flex-col text-right lg:flex-row">
        <form
          method="POST"
          data-netlify="true"
          name="contact"
          data-netlify-honeypot="bot-field"
          class="my-8 sm:max-w-lg sm:mx-auto lg:w-1/2"
        >
          <input type="hidden" name="form-name" value="contact" />
          <input
            type="text"
            name="name"
            id="name"
            placeholder="Nimi"
            class="mb-8 rounded-lg p-4 text-sm placeholder-brown placeholder-opacity-75 shadow-lg w-full"
          />
          <input
            type="email"
            name="email"
            id="email"
            placeholder="E-maili aadress"
            class="mb-8 rounded-lg p-4 text-sm placeholder-brown placeholder-opacity-75 shadow-lg w-full"
          />
          <textarea
            name="message"
            id="message"
            cols="30"
            rows="10"
            placeholder="Räägi meile oma lugu"
            class="mb-8 rounded-lg p-4 text-sm placeholder-brown placeholder-opacity-75 shadow-lg w-full"
          ></textarea>
          <button
            type="submit"
            class="uppercase text-base font-medium bg-white py-3 px-6 rounded-lg shadow-lg hover:shadow-none"
          >Saada</button>
        </form>
        <div class="lg:w-1/2">
          <div class="sm:flex sm:justify-between sm:max-w-sm sm:mx-auto lg:flex-col lg:justify-end">
            <div class="text-center my-8 sm:text-left lg:text-right">
              <span class="font-serif text-center text-lg">MTU Emale</span>
              <p class="mt-8 mb-4 font-light text-sm opacity-75">reg.nr. 80571306</p>
              <p class="mb-4 font-light text-sm opacity-75">
                Tallinn
                <span class="mx-2">|</span>11413
              </p>
            </div>
            <div class="text-center my-8 sm:text-right">
              <span class="font-serif text-center text-lg">Toeta meid</span>
              <p class="mt-8 uppercase text-sm">Lhv pank</p>
              <p class="mt-2 text-sm opacity-50 sm:overflow-x-auto">EE207700771004154508</p>
            </div>
          </div>
          <div class="w-10/12 mx-auto border border-white opacity-25 lg:hidden"></div>
          <div class="mt-8 text-center lg:max-w-sm lg:mx-auto lg:text-right">
            <span class="font-serif text-center text-lg">Jälgi meid sotsiaalmeedias</span>
            <div class="my-8 flex justify-center flex-row lg:justify-end">
              <a href="https://www.facebook.com/mtyEmale/">
                <img src="../assets/facebook-icon.svg" alt="Facebook icon" />
              </a>
              <a class="ml-8" href="https://www.instagram.com/mtuemale/">
                <img src="../assets/instagram-icon.svg" alt="Instragram icon" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-12 py-6 flex justify-center relative">
      <p class="text-sm opacity-50">@ 2020 MTÜ Emale</p>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
.container {
  width: 90%;
  max-width: 1088px;
  margin: auto;
  height: 100%;
  position: relative;
}

#footer-divider {
  position: absolute;
  top: -1px;
  width: 100%;
  height: 27px;
  background-image: url(../assets/header-section-divider.png);
  background-repeat: repeat-x;
  background-position: left;
  transform: rotate(180deg);
}

#footer-background-pattern {
  position: absolute;
  width: 100%;
  height: 100%;
  background-image: url(../assets/header-background-pattern.svg);
  background-repeat: repeat;
  z-index: 0;
  opacity: 0.5;
}
</style>