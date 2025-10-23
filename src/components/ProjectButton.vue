<template>
  <a :href="url" class="project-button" target="_blank" rel="noopener noreferrer">
    <img v-if="image" :src="image" :alt="text" class="button-image" />
    <span class="button-text">{{ text }}</span>
  </a>
</template>

<script setup>
defineProps({
  url: { type: String, required: true },
  image: { type: String, required: false },
  text: { type: String, required: true },
})
</script>

<style scoped>
.project-button {
  display: flex;
  align-items: center;
  justify-content: left;
  gap: 10px;
  padding: 10px 20px;
  border-radius: 5px;
  color: #ffffff;
  text-decoration: none;
  font-weight: bold;
  font-size: 1rem;

  /* --- EFECTO PROFESIONAL (Opción 2) --- */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  transform: translateY(0) scale(1);

  /* 1. Gradiente grande (tus colores + el original) */
  background: linear-gradient(135deg, #005f8d, #00aaff, #0077b5);
  /* 2. Fondo 300% más ancho */
  background-size: 300% 100%;
  /* 3. Empezamos en la posición '100%' (mostrando #0077b5) */
  background-position: 100% 0;

  transition:
    background-position 0.4s ease-out,
    /* Animamos la posición */ transform 0.3s ease-out,
    box-shadow 0.3s ease-out;
  /* --------------------------------- */

  cursor: pointer;
  max-width: 300px;
  width: 100%;
  text-align: center;
  will-change: transform, box-shadow, background-position;
}

.project-button:hover {
  /* 4. Movemos el fondo a '0' (mostrando el gradiente) */
  background-position: 0 0;

  /* Combinamos con el "levantamiento" */
  transform: translateY(-3px) scale(1.03);
  box-shadow: 0 7px 14px rgba(0, 0, 0, 0.25);
}

.button-image {
  width: 20px;
  height: 20px;
}

.button-text {
  display: inline-block;
}
</style>
