<script setup lang="ts">
import { onMounted, ref } from 'vue';
import navComponent from '~/components/navPrincipal.vue';

const title = ref(null)
const subtitle = ref(null)
const navbar = ref(null)
const disponibles = ref(null)


onMounted(() => {
  // Desplazar automáticamente hacia arriba al cargar la página
  window.scrollTo(0, 0);

  title.value = document.getElementById('title');
  subtitle.value = document.getElementById('subtitle');
  navbar.value = document.querySelector('.navbar');
  disponibles.value = document.getElementById('JuegosdisponiblesTitulo');


  setTimeout(() => {
    if (title.value) {
      title.value.classList.add('animate-title');
    }
    if (subtitle.value) {
      subtitle.value.classList.add('animate-subtitle');
    }
  }, 1500); // Inicia la animación después de 1.5 segundos

  setTimeout(() => {
    if (navbar.value) {
      navbar.value.classList.remove('hidden');
      navbar.value.classList.add('visible');
    }
  }, 3000); // Inicia la animación después de 3 segundos

  setTimeout(() => {
    if (disponibles.value) {
      disponibles.value.classList.remove('hidden');
      disponibles.value.classList.add('visible');
    }
  }, 4000); // Inicia la animación después de 4 segundos
});
</script>


<template>
  <div id="bg">
    <navComponent class="hidden" />
    <div id="tipografia">
      <div id="textosTitulos">
        <h1 id="title">¡Bienvenid@ A PixelArcade!</h1>
        <h5 id="subtitle">Donde revivir tu infancia es posible con dos clicks</h5>
      </div>
      <div class="hidden" id="JuegosdisponiblesTitulo">
        <h1 id="disponiblesJuegos">juegos disponibles</h1>
        <img src="../public/img/flecha.png" id="flechaJuegos" class="flecha" alt="Flecha señalando hacia abajo">
      </div>

      <!--*COMIENZO DE EL CONTENEDOR PACMAN-->
      <div id="ContenedorPacman">
        <p id="tittlePacman">¡Pacman!</p>
        <div>
          <img src="" id="gifPacman">
        </div>
        <div class="botonjugar">
          <button type="button" class="btn btn-outline-warning" id="botonPacman">¡Juega ahora!</button>
        </div>
      </div>
      <!--*FINAL DE EL CONTENEDOR PACMAN-->

      <!--*COMIENZO DE EL CONTENEDOR SPACE INVADERS-->
      <div id="ContenedorSpaceInvaders">
        <p id="tittleSpaceInvaders">¡Space Invaders!</p>
        <div>
          <img src="" id="gifSpaceInvaders">
        </div>
        <div class="botonjugar">
          <button type="button" class="btn btn-outline-warning" id="botonSpaceInvaders">¡Juega ahora!</button>
        </div>
      </div>
      <!--*FINAL DE EL CONTENEDOR SPACE INVADERS-->

      <!--*COMIENZO DE EL CONTENEDOR PING PONG-->
      <div id="ContenedorPingPong">
        <p id="tittlePingPong">¡Ping Pong Atari!</p>
        <div>
          <img src="" id="gifPingPong">
        </div>
        <div class="botonjugar">
          <button type="button" class="btn btn-outline-warning" id="botonPingPong">¡Juega ahora!</button>
        </div>
      </div>
      <!--*FINAL DE EL CONTENEDOR PING PONG-->
    </div>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

/* CONTENEDOR PACMAN */
#ContenedorPacman {
  margin-top: 12%;
  background-color: #000;
  min-height: 80vh;
  color: white;
  font-size: larger;
  box-shadow: rgb(238, 255, 0) 0 0 20px;
}

#tittlePacman {
  text-align: center;
  font-size: larger;
  padding-top: 2%;
}

#gifPacman {
  padding-left: 24%;
}

.botonjugar {
  display: grid;
  place-content: center;
  padding-top: 24%;
}

/* CONTENEDOR SPACE INVADERS */
#ContenedorSpaceInvaders {
  margin-top: 12%;
  background-color: #000;
  min-height: 80vh;
  color: white;
  font-size: larger;
  box-shadow: rgb(0, 255, 0) 0 0 20px;
}

#tittleSpaceInvaders {
  text-align: center;
  font-size: larger;
  padding-top: 2%;
}

#gifSpaceInvaders {
  padding-left: 24%;
}

/* CONTENEDOR PING PONG */
#ContenedorPingPong {
  margin-top: 12%;
  background-color: #000;
  min-height: 80vh;
  color: white;
  font-size: larger;
  box-shadow: rgb(255, 255, 255) 0 0 20px;
}

#tittlePingPong {
  text-align: center;
  font-size: larger;
  padding-top: 2%;
}

#gifPingPong {
  padding-left: 24%;
}

/* JUEGOS DISPONIBLES TEXTO Y FLECHA */
#JuegosdisponiblesTitulo {
  text-align: center;
  padding-top: 10%;
}

#disponiblesJuegos {
  color: white;
  font-size: 20px;
  text-shadow: 0 0 15px #00d9ff;
}

#flechaJuegos {
  max-width: 100px;
  filter: drop-shadow(0 0 5px #00d9ff);
  max-height: 80px;
}

@keyframes bounce {

  0%,
  20%,
  50%,
  80%,
  100% {
    transform: translateY(0);
  }

  40% {
    transform: translateY(10px);
  }

  60% {
    transform: translateY(5px);
  }
}

.flecha {
  width: 50px;
  /* Ajusta el tamaño según sea necesario */
  animation: bounce 2s infinite;
}

#bg {
  background: #17153B;
  min-height: 100vh;
  position: relative;
  overflow: hidden;
}

#tipografia {
  font-family: "Press Start 2P";
  text-transform: uppercase;
}

#textosTitulos {
  text-align: center;
  padding-top: 20%;

}

/* FONDO, TIPOGRAFIA GENERAL*/
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

/* TITULO PRINCIPAL */

/* Animaciones */
.animate-title {
  transform: translateY(-300px);
}

.animate-subtitle {
  transform: translateY(-300px);
}

.hidden {
  opacity: 0;
  transition: 1s ease-out;
}

.visible {
  opacity: 1;
  transition: 1s ease-in;
}

.no-transition {
  transition: none !important;
}

/* Animaciones */


/* Animaciones para el contenedor de Pacman */
</style>
