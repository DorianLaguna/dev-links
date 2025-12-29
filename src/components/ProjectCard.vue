<template>
  <div class="project-card">
    <div class="card-content">
      <h3 class="card-title">{{ title }}</h3>
      <p class="card-description">{{ description }}</p>
      <a :href="url" class="card-cta" target="_blank" rel="noopener noreferrer">
        {{ buttonText }}
        <span class="arrow">→</span>
      </a>
    </div>
    <div class="card-decoration"></div>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  url: {
    type: String,
    required: true,
  },
  buttonText: {
    type: String,
    default: 'Ver Proyecto',
  },
})
</script>

<style scoped>
.project-card {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  padding: 24px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  overflow: hidden;
  position: relative;
  width: 100%;
  max-width: 400px;
  margin: 0 auto;
  text-align: left;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  border-color: rgba(255, 255, 255, 0.4);
}

.card-title {
  margin: 0 0 12px 0;
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  background: linear-gradient(90deg, #fff, #a5b4fc);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.card-description {
  margin: 0 0 24px 0;
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.5;
}

.card-cta {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 20px;
  background: white;
  color: #4f46e5;
  text-decoration: none;
  border-radius: 8px;
  font-weight: 600;
  transition: all 0.2s ease;
}

.card-cta:hover {
  background: #eef2ff;
  gap: 12px;
}

.arrow {
  transition: transform 0.2s ease;
}

.card-decoration {
  position: absolute;
  top: -50px;
  right: -50px;
  width: 100px;
  height: 100px;
  background: radial-gradient(circle, rgba(79, 70, 229, 0.4) 0%, transparent 70%);
  border-radius: 50%;
  pointer-events: none;
}
</style>
