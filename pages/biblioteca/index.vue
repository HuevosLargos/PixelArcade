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
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

#carta {
  max-width: 85%;
  padding-left: 20%;
  padding-top: 25%;
  display: flex;
  overflow: hidden;
  position: relative;
  justify-content: center;
}

#bg {
  background: #000;
  min-height: 100vh;
  font-family: "Press Start 2P";
  font-size: large;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

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
  color: white;
  font-size: 2rem;
  cursor: pointer;
}

#selectortxt {
  padding-bottom: 4%;
}

.boton-2 {
  display: flex;
}

.btn-2 {
  text-decoration: none;
  background-color: #e1ad12;
  color: rgb(49, 49, 49);
  padding: 10px 20px;
  border-radius: 20px;
  transition: all .3s ease;
}

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
}
</style>
