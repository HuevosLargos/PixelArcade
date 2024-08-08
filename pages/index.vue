<template>
  <div id="bg">
    <navComponent class="navbar hidden" />
    <div id="tipografia">
      <div id="textosTitulos">
        <h1 id="title">¡Bienvenid@ A PixelArcade!</h1>
        <h5 id="subtitle">Donde revivir tu infancia es posible con dos clicks</h5>
      </div>
      <div class="hidden" id="JuegosdisponiblesTitulo">
        <h1 id="disponiblesJuegos">juegos disponibles</h1>
        <img src="../public/img/flecha.png" id="flechaJuegos" class="flecha" alt="Flecha señalando hacia abajo">
      </div>
      <div id="ContenedorPacman">
        <p id="txtPacman">¡Pacman!</p>
        <div>
          <img src="../public/img/Pacman.gif">
        </div>
      </div>
    </div>
    <div id="stars"></div>
  </div>
</template>

<script lang="ts">
export default {
  mounted() {
    const title = document.getElementById('title');
    const subtitle = document.getElementById('subtitle');
    const navbar = document.querySelector('.navbar');
    const disponibles = document.getElementById('JuegosdisponiblesTitulo');
    // Hacer el nav invisible al principio sin transición
    navbar.classList.add('no-transition');
    disponibles.classList.add('no-transition');

    setTimeout(() => {
      title.classList.add('animate-title');
      subtitle.classList.add('animate-subtitle');
    }, 1500); // Inicia la animación después de 1.5 segundos

    // Hacer el nav visible después de 1 segundo
    setTimeout(() => {
      navbar.classList.remove('hidden', 'no-transition');
      navbar.classList.add('visible');
    }, 3000); // Inicia la animación después de 3 segundos

    setTimeout(() => {
      disponibles.classList.remove('hidden', 'no-transition');
      disponibles.classList.add('visible');
    }, 4000); // Inicia la animación después de 3 segundos

    // Crear estrellas
    const stars = document.getElementById('stars');
    for (let i = 0; i < 100; i++) {
      const star = document.createElement('div');
      star.classList.add('star');
      star.style.left = `${Math.random() * 100}%`;
      star.style.top = `${Math.random() * 100}%`;
      stars.appendChild(star);
    }
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

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
  0%, 20%, 50%, 80%, 100% {
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
  width: 50px; /* Ajusta el tamaño según sea necesario */
  animation: bounce 2s infinite;
}

/* CONTENEDOR PACMAN */
#ContenedorPacman {
  margin-top: 30%;
  background-color: #000;
  margin-right: 40%;
  min-height: 40vh;
  border: solid;
  border-color: magenta;
  color: white;
  font-size: larger;
}

#txtPacman {
  text-align: center;
}

/* CONTENEDOR PACMAN */
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

/* Estrellas */
#stars {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.star {
  position: absolute;
  width: 2px;
  height: 2px;
  background: white;
  border-radius: 50%;
  animation: twinkle 2s infinite;
}

@keyframes twinkle {
  0%, 100% {
    opacity: 0.5;
  }
  50% {
    opacity: 1;
  }
}
</style>
