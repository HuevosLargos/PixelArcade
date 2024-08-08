<<<<<<< HEAD
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
=======
<template>
  <div id="bg">
    <h1 id="selectortxt">Selector de juegos</h1>
    <!--*SELECTOR DE JUEGOS-->
    <div class="row row-cols-1 row-cols-md-3 g-4" id="carta">
      <div class="col" v-for="(card, index) in cards" :key="index">
        <img :src="card.img" class="card-img-top" :class="{ active: index === currentCard }" />
        <p class="card-title">{{ card.title }}</p>
        <p class="card-text">{{ card.description }}</p>
      </div>
    </div>
    <!--*SELECTOR DE JUEGOS-->
    <!--*BOTON JUGAR-->
    <div class="buton-2">
      <a href="" class="btn-2">Jugar</a>
    </div>
    <!--*BOTON JUGAR-->

    <!--*FLECHAS PARA CAMBIAR DE JUEGO-->
    <div class="d-flex justify-content-center mt-1 w-100">
      <button @click="prevCard"><svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="none" viewBox="0 0 24 24">
  <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12l4-4m-4 4 4 4"/>
</svg>
</button>
      <button @click="nextCard">
        <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="none" viewBox="0 0 24 24">
  <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 12H5m14 0-4 4m4-4-4-4"/>
</svg>
</button>
    </div>
    <!--*FLECHAS PARA CAMBIAR DE JUEGO-->

  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          class: "card-1",
          img: require("../../public/img/pacman.png"),
          title: "Pacman",
          description: ""
        },
        {
          class: "card-2",
          img: require("../../public/img/Pong atari.png"),
          title: "Pong",
          description: ""
        },
        {
          class: "card-3",
          img: require("../../public/img/Space invaders.png"),
          title: "Space Invaders",
          description: ""
        },
      ],
      currentCard: 0,
      isTransitioning: false,
    };
  },
  methods: {
    nextCard() {
      if (!this.isTransitioning) {
        this.isTransitioning = true;
        setTimeout(() => {
          this.currentCard = (this.currentCard + 1) % this.cards.length;
          this.isTransitioning = false;
        }, 500); // 500ms delay
      }
    },
    prevCard() {
      if (!this.isTransitioning) {
        this.isTransitioning = true;
        setTimeout(() => {
          this.currentCard =
            (this.currentCard - 1 + this.cards.length) % this.cards.length;
          this.isTransitioning = false;
        }, 500); // 500ms delay
      }
    },
  },
>>>>>>> dfe172962f25eb85a859fc9accb4b6d5a72ccae8
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

<<<<<<< HEAD
=======
#carta {
  max-width: 85%;
  padding-left: 20%;
  padding-top: 25%;
  display: flex;
  overflow: hidden;
  position: relative;
  justify-content: center;
}

>>>>>>> dfe172962f25eb85a859fc9accb4b6d5a72ccae8
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

<<<<<<< HEAD
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
=======
.card-img-top {
  width: 100%;
  height: auto;
  max-width: 500px;
  min-height: 300px;
  box-shadow: white 0 0 20px;
  transition: opacity 0.5s ease-in-out;
  opacity: 0;
  position: absolute;
}

.card-img-top.active {
  opacity: 1;
}

button {
  background: none;
  border: none;
>>>>>>> dfe172962f25eb85a859fc9accb4b6d5a72ccae8
  color: white;
  text-align: center;
  padding-top: 14%;
  font-size: x-large;

}

<<<<<<< HEAD
.flecha {
  background-color: transparent;
  border: none;
  margin: 10px;
}

.shadow-box {
  box-shadow: 0 0 40px white;
=======
#selectortxt {
  padding-bottom: 4%;
}

.boton-2 {
  display: flex;
>>>>>>> dfe172962f25eb85a859fc9accb4b6d5a72ccae8
}

.btn-2 {
  text-decoration: none;
  background-color: #e1ad12;
  color: rgb(49, 49, 49);
  padding: 10px 20px;
  border-radius: 20px;
  transition: all .3s ease;
}

<<<<<<< HEAD
.buton-2 {
  margin-top: 10%;
=======
.btn-2:hover {
  background-color: #ffc000;
  color: #000;
  box-shadow: yellow 0 0 30px;
}

.card-title {
  color: white;
  text-align: center;
  font-size: x-large;
  padding-top: 10%;
}

.card-text {
  color: white;
  text-align: center;
  font-size: medium;
  padding-top: 5%;
>>>>>>> dfe172962f25eb85a859fc9accb4b6d5a72ccae8
}
</style>
