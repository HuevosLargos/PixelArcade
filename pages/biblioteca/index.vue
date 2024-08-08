<script setup lang="ts">
import { ref } from 'vue';
import navComponent from '~/components/navGeneral.vue';

const Juegos = ref([
  {
    class: "Juego-1",
    img: require("../../public/img/pacman.png"),
    title: "Pacman",
    description: ""
  },
  {
    class: "Juego-2",
    img: require("../../public/img/Pong atari.png"),
    title: "Pong",
    description: ""
  },
  {
    class: "Juego-3",
    img: require("../../public/img/Space invaders.png"),
    title: "Space Invaders",
    description: ""
  },
]);

const currentJuego = ref(0);
const isTransitioning = ref(false);

const nextJuego = () => {
  if (!isTransitioning.value) {
    isTransitioning.value = true;
    currentJuego.value = (currentJuego.value + 1) % Juegos.value.length;
    setTimeout(() => {
      isTransitioning.value = false;
    }, 500); // Duración de la animación
  }
};

const prevJuego = () => {
  if (!isTransitioning.value) {
    isTransitioning.value = true;
    currentJuego.value = (currentJuego.value - 1 + Juegos.value.length) % Juegos.value.length;
    setTimeout(() => {
      isTransitioning.value = false;
    }, 500); // Duración de la animación
  }
};
</script>

<template>
  <div id="bg">
    <navComponent />
    <div id="ContenedorJuegos" class="tipografia">
      <div v-for="(Juego, index) in Juegos" :key="index" id="Contenedor1" v-show="index === currentJuego">
        <img :src="Juego.img" class="card-img-top shadow-box rounded" id="imagen" />
        <h2 class="titulo">{{ Juego.title }}</h2>
        <button @click="prevJuego" class="btn btn-primary flecha"><svg class="w-6 h-6 text-white" aria-hidden="true"
            xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M5 12h14M5 12l4-4m-4 4 4 4" />
          </svg>
        </button>
        <button @click="nextJuego" class="btn btn-primary flecha"><svg class="w-6 h-6 text-white" aria-hidden="true"
            xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M19 12H5m14 0-4 4m4-4-4-4" />
          </svg>
        </button>
        <div class="buton-2">
          <a href="" class="btn-2 tipografia">Jugar</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

#bg {
  background: #000;
  min-height: 100vh;
}

#ContenedorJuegos {
  max-width: 700px;
  min-width: 700px;
  max-height: 700px;
  min-height: 700px;
  margin-left: 32%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

#imagen {}

#Contenedor1 {
  transition: opacity 0.5s ease;
  text-align: center;
}

.tipografia {
  font-family: "Press Start 2P";
  text-transform: uppercase;
}

.titulo {
  color: white;
  text-align: center;
  padding-top: 14%;
  font-size: x-large;

}

.flecha {
  background-color: transparent;
  border: none;
  margin: 10px;
}

.shadow-box {
  box-shadow: 0 0 40px white;
}

.btn-2 {
  text-decoration: none;
  background-color: #e1ad12;
  color: rgb(49, 49, 49);
  padding: 10px 20px;
  border-radius: 20px;
  transition: all .3s ease;
}

.buton-2 {
  margin-top: 10%;
}
</style>
