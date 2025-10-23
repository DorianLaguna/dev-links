<script setup>
import LinkButton from './components/LinkButton.vue'
import ProjectButton from './components/ProjectButton.vue'

const socialLinks = [
  {
    url: 'https://www.instagram.com/dorian.devs/',
    image: '/images/insta.png',
    text: 'Instagram',
  },
  {
    url: 'https://www.tiktok.com/@dorian.devs',
    image: '/images/tiktok.png',
    text: 'TikTok',
  },
  {
    url: 'https://github.com/DorianLaguna',
    image: '/images/github.png',
    text: 'GitHub',
  },
  {
    url: 'https://www.linkedin.com/in/dorian-laguna/',
    image: '/images/linkedin.png',
    text: 'LinkedIn',
  },
]

const additionalLinks = [
  {
    url: 'https://www.share-prompts.com/',
    text: '🤖 Proyecto Prompts',
  },
  {
    url: 'https://curriculum.dev-dorian-laguna.com/',
    text: '📄 Curriculum',
  },
  {
    url: 'https://rubikgraph.dev-dorian-laguna.com/',
    text: '🧊 Cubo rubik 3D',
  },
]
</script>

<template>
  <div id="app">
    <!-- Imagen de la marca personal -->
    <div class="brand-image">
      <img src="/images/yo.jfif" alt="Marca Personal" />
    </div>

    <!-- Sección de enlaces a redes sociales -->
    <div class="social-links">
      <div class="social-links-container">
        <LinkButton
          v-for="(link, index) in socialLinks"
          :key="index"
          :url="link.url"
          :image="link.image"
        />
      </div>
    </div>

    <!-- Sección de enlaces adicionales -->
    <div class="additional-links">
      <div class="additional-links-container">
        <ProjectButton
          v-for="(link, index) in additionalLinks"
          :key="index"
          :url="link.url"
          :image="link.image"
          :text="link.text"
        />
      </div>
    </div>
  </div>
</template>

<style>
html,
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box; /* Buena práctica */
}
</style>

<style scoped>
/* Estilos generales */
#app {
  text-align: center;
  font-family: 'Roboto', Arial, sans-serif;
  background: radial-gradient(circle at 20% 10%, #ff0000, #7a00ff, #00004d);
  color: #ffffff;
  min-height: 100vh;
  padding: 20px;
}

/* Imagen de la marca personal */
.brand-image img {
  width: 150px;
  height: 150px;
  object-fit: cover;
  border-radius: 50%;
  margin: 20px auto;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease;
}

.brand-image img:hover {
  transform: scale(1.1);
}

/* Redes sociales (horizontal) */
.social-links {
  margin: 10px auto; /* Reducir el margen para mantener la estética */
  padding: 0; /* Eliminar el contenedor blanco */
}

.social-links-container {
  display: flex;
  justify-content: center;
  gap: 15px;
}

/* Enlaces adicionales (vertical) */
.additional-links {
  margin: 10px auto; /* Reducir el margen para mantener la estética */
  padding: 0; /* Eliminar el contenedor blanco */
}

.additional-links-container {
  display: flex;
  flex-direction: column;
  align-items: center; /* Centrar los botones horizontalmente */
  justify-content: center; /* Asegurar el centrado vertical si es necesario */
  gap: 15px;
  width: 100%; /* Asegurar que ocupe todo el ancho disponible */
}
</style>
