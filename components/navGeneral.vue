<template>
  <nav class="navbar contracted navbar-expand-lg shadow-lg">
    <div class="container">
      <div class="navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="/biblioteca" id="game"><strong>Juegos</strong></a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" href="/contactanos" id="contact"><strong>Contactanos</strong></a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" href="/sobreNosotros" id="about"><strong>Info</strong></a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" href="/sobreNosotros" id="username"><strong>Records</strong></a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

.navbar.expanded .cart img {
  transition: 0.5s ease;
  filter: brightness(0) invert(0.8) !important;
}

.white-text {
  color: #c7c7c7 !important;
}

.navbar {
  overflow: hidden;
  background-color: #fff;
  transition: background-color 0.5s ease;
  /* Añade esto */
}

.navbar.expanded {
  height: 10em;
  transition: 0.5s ease;
  /* Cambia esto al tamaño que prefieras cuando el ratón está encima */
}


.navbar.contracted {
  height: 5em;
  transition: 0.5s ease;
  /* Cambia esto al tamaño que prefieras cuando el ratón no está encima */
}

.navbar:hover {
  background-color: #433D8B;
  /* Cambia esto al color gris oscuro que prefieras */
}

#contact:hover {
  color: #ffee00 !important;
  filter: drop-shadow(0 0 10px #c5b800);
  transition: filter 0.3s ease;
}

#about:hover {
  color: #ff0000 !important;
  filter: drop-shadow(0 0 10px #a50000);
  transition: filter 0.3s ease;
}

#username:hover {
  color: #00eeff !important;
  filter: drop-shadow(0 0 10px #009da8);
  transition: filter 0.3s ease;
}

#game:hover {
  color: #33ff00 !important;
  filter: drop-shadow(0 0 10px #1f9900);
  transition: filter 0.3s ease;
}

.nav-link {
  font-family: "Press Start 2P";
  font-size: 16px;
  color: #000000;
  text-transform: uppercase;
  transition: color 0.5s ease;
}

.cart {
  margin-bottom: 0.5em;
  transition: filter 0.3s ease;

}

.navbar-nav {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  height: 50px;
  transition: height 0.3s ease;
  margin-right: 26.5%;
}

.nav-item {
  padding: 0 15px;
}

.navbar-toggler-icon {
  background-image: url("data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAiIGhlaWdodD0iOCIgdmlld0JveD0iMCAwIDIwIDgiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGc+PHBhdGggZmlsbD0iIzMzMyIgZD0iTTYuNSA5LjQzOWw1LjkyIDUuOTIgNS45Mi01LjkyLTUuOTItNS45MiA1LjkyLTUuOTItNS45Mi01LjkyLTUuOTIgNS45MiA1LjkyLTUuOTJ6Ii8+PC9nPjwvc3ZnPg==");
}

@media (max-width: 992px) {
  .navbar-nav {
    flex-direction: column;
    height: auto;
  }

  .nav-item {
    padding: 10px 0;
  }
}
</style>

<script>
export default {
  mounted() {
    const nav = document.getElementsByClassName("navbar")[0];
    const links = document.querySelectorAll(".nav-link");

    setTimeout(() => {
      nav.addEventListener("mouseenter", () => {
        nav.classList.remove("contracted");
        nav.classList.add("expanded");
        links.forEach((link) => {
          link.classList.add("white-text");
        });
      });

      nav.addEventListener("mouseleave", () => {
        nav.classList.remove("expanded");
        nav.classList.add("contracted");
        links.forEach((link) => {
          link.classList.remove("white-text");
        });
      });
    },); // Delay de 2 segundos
  },
};
</script>
