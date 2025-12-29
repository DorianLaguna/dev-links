<script setup>
import LinkButton from './components/LinkButton.vue'
import ProjectCard from './components/ProjectCard.vue'

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

const projects = [
  {
    title: 'Ramo Eterno',
    description: 'Plataforma de regalos digitales con renderizado 3D y pagos seguros. Una experiencia única para momentos especiales.',
    url: 'https://regalo.dev-dorian-laguna.com',
    buttonText: 'Ver Proyecto'
  },
  {
    title: 'Proyecto Prompts AI',
    description: 'Plataforma colaborativa para compartir y descubrir los mejores prompts para Inteligencia Artificial.',
    url: 'https://www.share-prompts.com/',
    buttonText: 'Ver Proyecto'
  },
  {
    title: 'Cubo Rubik 3D',
    description: 'Simulador interactivo de cubo Rubik desarrollado con tecnologías web modernas.',
    url: 'https://rubikgraph.dev-dorian-laguna.com/',
    buttonText: 'Ver Proyecto'
  }
]
</script>

<template>
  <div id="app">
    <main class="content-wrapper">
      <!-- Encabezado (Hero) -->
      <section class="hero-section">
        <div class="brand-image">
          <img src="/images/yo.jfif" alt="Dorian Laguna - Desarrollador Backend" />
        </div>
        <div class="hero-text">
          <h1>Dorian Laguna <span class="separator">|</span> <span class="subtitle">Ing. en Diseño de Software y Redes</span></h1>
          <p class="tagline">Especialista en desarrollo backend y experiencia digital</p>
        </div>

        <!-- Redes sociales (Hero) -->
        <div class="social-links">
          <LinkButton
            v-for="(link, index) in socialLinks"
            :key="index"
            :url="link.url"
            :image="link.image"
          />
        </div>
      </section>

      <!-- Sección "Mis Proyectos" -->
      <section class="products-section">
        <h2 class="section-title">Mis Proyectos</h2>
        <div class="cards-container">
          <ProjectCard 
            v-for="(project, index) in projects"
            :key="index"
            :title="project.title"
            :description="project.description"
            :url="project.url"
            :buttonText="project.buttonText"
          />
        </div>
      </section>

      <!-- Sección "Perfil Profesional" -->
      <section class="profile-section">
        <h2 class="section-title">Perfil Profesional</h2>
        <div class="cards-container">
          <ProjectCard 
            title="Portafolio y CV"
            description="Explora mi trayectoria profesional, certificaciones y proyectos destacados en el ecosistema tecnológico."
            url="https://curriculum.dev-dorian-laguna.com/"
            buttonText="Ver Trayectoria"
          />
        </div>
      </section>
    </main>

    <!-- Footer Legal -->
    <footer class="legal-footer">
      <div class="footer-content">
        <p>&copy; 2025 Dorian Laguna. Todos los derechos reservados.</p>
      </div>
    </footer>
  </div>
</template>

<style>
/* Reset básico mejorado */
html, body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', 'Roboto', sans-serif; /* Preferencia por Inter si está disponible */
  background-color: #0f172a; /* Fondo base oscuro por si falla el gradiente */
  min-height: 100vh;
}
</style>

<style scoped>
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background: radial-gradient(circle at 50% 0%, #2e1065, #0f172a, #000000);
  color: #f8fafc;
}

.content-wrapper {
  flex: 1;
  max-width: 800px;
  margin: 0 auto;
  padding: 40px 20px;
  width: 100%;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  gap: 48px;
}

/* --- Hero Section --- */
.hero-section {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
}

.brand-image img {
  width: 140px;
  height: 140px;
  object-fit: cover;
  border-radius: 50%;
  border: 3px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 0 20px rgba(124, 58, 237, 0.3);
  transition: transform 0.3s ease;
}

.brand-image img:hover {
  transform: scale(1.05);
  border-color: rgba(124, 58, 237, 0.5);
}

.hero-text h1 {
  font-size: 1.5rem; /* Ajustado para móviles, escalará en desktop */
  font-weight: 700;
  margin: 0;
  line-height: 1.4;
  letter-spacing: -0.02em;
}

.hero-text .separator {
  color: #6366f1;
  margin: 0 8px;
}

.hero-text .subtitle {
  color: #e2e8f0;
  font-weight: 400;
  display: block; /* En móviles queda mejor abajo */
  font-size: 1.1rem;
  margin-top: 4px;
}

.tagline {
  color: #94a3b8;
  font-size: 0.95rem;
  margin: 0;
  max-width: 600px;
}

.social-links {
  margin-top: 12px;
  display: flex;
  gap: 20px;
  justify-content: center;
}

/* --- Headings --- */
.section-title {
  text-align: center;
  font-size: 1.5rem;
  margin-bottom: 24px;
  color: #ffffff;
  position: relative;
  display: inline-block;
  width: 100%;
}

.section-title::after {
  content: '';
  display: block;
  width: 40px;
  height: 3px;
  background: #6366f1;
  margin: 8px auto 0;
  border-radius: 2px;
}

.subsection-title {
  text-align: center;
  color: #94a3b8;
  font-size: 1.1rem;
  margin-bottom: 16px;
  font-weight: 500;
}

/* --- Products & Profile Sections --- */
.products-section, .profile-section {
  width: 100%;
}

.cards-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

/* --- Additional Links --- */
.additional-links-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  width: 100%;
}

/* --- Footer --- */
.legal-footer {
  background: #000000;
  padding: 30px 20px;
  text-align: center;
  margin-top: auto;
  border-top: 1px solid rgba(255, 255, 255, 0.05);
}

.footer-content p {
  color: #64748b;
  font-size: 0.85rem;
  margin: 0 0 10px 0;
}

.legal-link {
  color: #94a3b8;
  font-size: 0.85rem;
  text-decoration: none;
  transition: color 0.2s;
}

.legal-link:hover {
  color: #ffffff;
  text-decoration: underline;
}

/* --- Responsive Adjustments --- */
@media (min-width: 640px) {
  .hero-text h1 {
    font-size: 1.75rem;
  }
  
  .hero-text .subtitle {
    display: inline;
  }
}
</style>

