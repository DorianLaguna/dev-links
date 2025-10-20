<script setup>
const props = defineProps({
  url: {
    type: String,
    required: true,
  },
  image: {
    type: String,
    required: false,
  },
})
</script>

<template>
  <a :href="props.url" class="social-icon-link" target="_blank" rel="noopener noreferrer">
    <img :src="props.image" alt="icono de red social" class="social-icon-image" />
  </a>
</template>

<style scoped>
.social-icon-link {
  display: inline-block; /* Permite que el enlace se ajuste al tamaño de la imagen */
  /* --- ELIMINAMOS TODOS LOS ESTILOS DE BOTÓN DE AQUÍ --- */
  /* padding: 12px; */
  /* border-radius: 50%; */
  /* background-color: #0077b5; */
  /* box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2); */
  /* will-change: transform, box-shadow; */
  /* ---------------------------------------------------- */

  /* Mantendremos las transiciones y el hover para la imagen directamente */
  transition:
    transform 0.3s ease-out,
    filter 0.3s ease-out; /* Nueva: filter */
  will-change: transform, filter;
}

.social-icon-image {
  width: 32px; /* <-- CAMBIO: Un poco más grande para que se vea mejor */
  height: 32px; /* <-- CAMBIO */
  display: block;
  filter: grayscale(0%); /* <-- Nueva: imagen a color por defecto */
  transition:
    transform 0.3s ease-out,
    filter 0.3s ease-out; /* <-- Nueva: filter */
}

.social-icon-link:hover .social-icon-image {
  transform: scale(1.15); /* Aumenta un poco más */
  filter: grayscale(0%) brightness(1.1); /* <-- Nueva: un pequeño brillo en hover */
  /* --- ELIMINAMOS LOS ESTILOS DE BACKGROUND Y SHADOW DEL HOVER --- */
  /* background-color: #005f8d; */
  /* box-shadow: 0 7px 14px rgba(0, 0, 0, 0.25); */
  /* ----------------------------------------------------------------- */
}
</style>
