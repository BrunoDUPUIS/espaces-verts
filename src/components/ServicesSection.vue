<template>
  <section id="services" class="services">
    <h2>Nos Services</h2>

    <div class="services-track" ref="track">
      <div class="card">🌿 Tonte de pelouse</div>
      <div class="card">🌳 Taille de haies</div>
      <div class="card">🌾 Débroussaillage</div>
      <div class="card">🪵 Sciage d’arbres tombés</div>
      <div class="card">🔥 Fendage de bois</div>
      <div class="card">🚛 Évacuation des déchets</div>
      <div class="card">🌱 Entretien complet jardin</div>

      <!-- duplication pour effet boucle fluide -->
      <div class="card">🌿 Tonte de pelouse</div>
      <div class="card">🌳 Taille de haies</div>
      <div class="card">🌾 Débroussaillage</div>
    </div>
  </section>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const track = ref(null)

onMounted(() => {
  let speed = 0.5 // 🔥 vitesse lente (plus petit = plus lent)

  const animate = () => {
    if (!track.value) return

    track.value.scrollLeft += speed

    // boucle infinie propre
    if (track.value.scrollLeft >= track.value.scrollWidth / 2) {
      track.value.scrollLeft = 0
    }

    requestAnimationFrame(animate)
  }

  animate()
})
</script>

<style scoped>
.services {
  padding: 80px 20px;
  background: #f5f7f5;
  text-align: center;
}

.services-track {
  margin-top: 40px;
  display: flex;
  gap: 20px;

  overflow-x: hidden;
  scroll-behavior: smooth;
}

.card {
  flex: 0 0 auto;
  min-width: 220px;

  background: white;
  padding: 30px 20px;
  border-radius: 18px;

  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);

  font-weight: 600;
  font-size: 1rem;

  border-left: 4px solid #2e7d32;

  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-6px);
}

/* effet fade sur les bords (pro) */
.services {
  position: relative;
}

.services::before,
.services::after {
  content: '';
  position: absolute;
  top: 0;
  width: 80px;
  height: 100%;
  z-index: 2;
  pointer-events: none;
}

.services::before {
  left: 0;
  background: linear-gradient(to right, #f5f7f5, transparent);
}

.services::after {
  right: 0;
  background: linear-gradient(to left, #f5f7f5, transparent);
}

@media (max-width: 768px) {
  .card {
    min-width: 200px;
  }
}
</style>
