<template>
  <section id="motivation-section" class="mt-20 font-sans font-light text-brown">
    <div class="mb-16">
      <h1 class="font-serif text-center text-xl">Mis on meie motivatsioon?</h1>
      <img class="mx-auto" src="../assets/heading-line.svg" alt="Line under heading" />
    </div>
    <div class="container">
      <div class="flex flex-col lg:flex-row-reverse">
        <!-- Motivation content -->
        <div class="text-base sm:max-w-md sm:mx-auto lg:w-1/2 lg:text-xl">
          <p
            class="mb-8 tracking-wide leading-6 sm:text-center lg:text-left leading-8"
          >Kui sünnib laps siis tema side emaga on juba eostamisest alates tugev.</p>
          <p
            class="mb-8 tracking-wide leading-6 sm:text-center lg:text-left leading-8"
          >Beebi kasvab kuuldes tema häält ja südametukseid. Nendest helidest saavad lapse jaoks turvatunde loojad.</p>
          <p
            class="mb-8 tracking-wide leading-6 sm:text-center lg:text-left leading-8"
          >Kui laps saab ka peale sündi ema rinnale siis teda rahustab nii ema lõhn, kui helid, mida ta kuuleb. Igati loomulik on see, et ema hoolitseb lapse eest.</p>
          <p
            class="mb-16 tracking-wide leading-6 sm:text-center lg:text-left leading-8"
          >See side on ilus ja vajalik, et kasvaks ja areneks terve ning tasakaalukas inimene. Psühholoogid ning teadlased kinnitavad, et laps vajab kasvamiseks turvalisi lähisuhteid enda ümber.</p>
        </div>
        <!-- Motivation image -->
        <div class="mb-16 sm:max-w-md sm:mx-auto lg:w-1/2 lg:flex lg:items-center">
          <img src="../assets/motivation-image.svg" alt="Motivation section image" />
        </div>
      </div>
      <!-- Scroll-down indicator -->
    </div>
    <div class>
      <img class="mx-auto" src="../assets/arrow_down.svg" alt="Scroll down indicator" />
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
}
</style>