<script lang="ts">
export default {
  mounted() {
    const title = document.getElementById('title');
    const subtitle = document.getElementById('subtitle');
    const navbar = document.querySelector('.navbar');

    // Hacer el nav invisible al principio
    navbar.classList.add('navbar-hidden');

    setTimeout(() => {
      title.classList.add('animate-title');
      subtitle.classList.add('animate-subtitle');
    }, 1500); // Inicia la animación después de 1.5 segundos

    // Hacer el nav visible después de 1 segundo
    setTimeout(() => {
      navbar.classList.remove('navbar-hidden');
      navbar.classList.add('navbar-visible');
    }, 3000); // Inicia la animación después de 3 segundo
  }
}
</script>
<script setup lang="ts">
import navComponent from '~/components/navPrincipal.vue';

</script>
<template>
  <div id="bg">
    <navComponent />
    <div id="textos">
      <h1 id="title">¡Bienvenid@ A PixelArcade!</h1>
      <h5 id="subtitle">Donde revivir tu infancia es posible con dos clicks</h5>
    </div>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

#bg {
  background: #17153B;
  min-height: 100vh;
}

#textos {
  text-align: center;
  padding-top: 20%;
  font-family: "Press Start 2P";
  text-transform: uppercase;
}

#title {
  color: white;
  font-size: xx-large;
  transition: all 2s ease;
}

#subtitle {
  color: rgb(141, 140, 140);
  font-size: medium;
  transition: all 2s ease;
}

.animate-title {
  transform: translateY(-300px);
}

.animate-subtitle {
  transform: translateY(-300px);
}

.navbar-hidden {
  opacity: 0;
}

.navbar-visible {
  opacity: 1;
  transition: opacity 1s ease-in-out;
}
</style>
