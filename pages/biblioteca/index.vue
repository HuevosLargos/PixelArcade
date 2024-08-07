<template>
  <div id="bg">
      <h1 id="selectortxt">
          Selector de juegos
      </h1>
    <div class="row row-cols-1 row-cols-md-3 g-4" id="carta">
      <div class="col" v-for="(card, index) in cards" :key="index">
        <div :class="['card', card.class, { active: index === currentCard, left: index === (currentCard - 1 + cards.length) % cards.length, right: index === (currentCard + 1) % cards.length }]">
          <img :src="card.img" class="card-img-top" />
          <div class="card-body">
            <p class="card-title">{{ card.title }}</p>
          </div>
        </div>
      </div>
    </div>
    <div class="controls">
      <button @click="prevCard">⬅️</button>
      <button @click="nextCard">➡️</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        { class: 'card-1', img: require('../../public/img/pacman.png'), title: 'Pacman' },
        { class: 'card-2', img: require('../../public/img/Pong atari.png'), title: 'Pong' },
        { class: 'card-3', img: require('../../public/img/Space invaders.png'), title: 'Space invaders' }
      ],
      currentCard: 0,
      isTransitioning: false
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
          this.currentCard = (this.currentCard - 1 + this.cards.length) % this.cards.length;
          this.isTransitioning = false;
        }, 500); // 500ms delay
      }
    }
  }
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

.card {
  min-width: 100%;
  transition: transform 0.5s ease;
  position: absolute;
  top: 0;
  left: 0;
}

.card img {
  width: 100%;
  height: auto;
}

.card.active {
  transform: translateX(0);
  z-index: 2;
}

.card.left {
  transform: translateX(-100%);
  z-index: 1;
}

.card.right {
  transform: translateX(100%);
  z-index: 1;
}

.card-1 {
  background-color: #433d8b;
}

.card-2 {
  background-color: #41b06e;
}

.card-3 {
  background-color: #5f374b;
}

.controls {
  display: flex;
  justify-content: center;
  width: 100%;
  margin-top: 20px;
}

button {
  background: none;
  border: none;
  color: white;
  font-size: 2rem;
  cursor: pointer;
}
#selectortxt{
  padding-bottom: 3%;
}
</style>
