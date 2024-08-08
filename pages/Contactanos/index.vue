<script setup lang="ts">
import navComponent from '~/components/navGeneral.vue';

</script>
<template>
  <div id="bg">
    <navComponent />
    <p id="texto"><b>Esta pagina es un proyecto para practicar hecho por dos alumnos, no esta creada con el objetivo de
        lucrarse o de suplantar la imagen de los creadores originales de los juegos que recreamos, queremos que se vea
        de una manera enfocada al aprendizaje y nada mas.</b></p>
  </div>

</template>
<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

#texto {
  text-align: center;
  padding-top: 5%;
  font-size: 15px;
  font-family: "Press Start 2P";
  padding-left: 5%;
  padding-right: 5%;
  color: white;
}
#bg {
  min-height: 100vh;
  background: #17153B;
}
</style>
