<template>
  <section id="services" class="services">
    <h2>Nos Services</h2>

    <div class="services-track" ref="track">
      <div class="card">🌿 Tonte de pelouse</div>
      <div class="card">🌳 Taille de haies</div>
      <div class="card">🌾 Débroussaillage</div>
      <div class="card">🪵 Sciage d’arbres tombés</div>
      <div class="card">🔥 Fendage de bois</div>
      <div class="card">🚛 Évacuation déchets</div>
      <div class="card">🌱 Entretien complet jardin</div>
    </div>
  </section>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const track = ref(null)

onMounted(() => {
  const isMobile = window.innerWidth < 768

  // ❌ STOP auto-scroll sur mobile (important)
  if (isMobile) return

  let speed = 0.4

  const animate = () => {
    if (!track.value) return

    track.value.scrollLeft += speed

    // boucle fluide
    if (track.value.scrollLeft >= track.value.scrollWidth - track.value.clientWidth) {
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
  overflow: hidden;
}

.services-track {
  margin-top: 40px;
  display: flex;
  gap: 16px;

  overflow-x: auto;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;

  padding-bottom: 10px;
}

/* cache scrollbar */
.services-track::-webkit-scrollbar {
  display: none;
}

.card {
  flex: 0 0 auto;

  /* 🔥 RESPONSIVE CLEAN */
  width: clamp(180px, 60vw, 240px);

  background: white;
  padding: 25px 18px;
  border-radius: 16px;

  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);

  font-weight: 600;

  scroll-snap-align: start;

  border-left: 4px solid #2e7d32;

  transition: transform 0.25s ease;
}

.card:hover {
  transform: translateY(-5px);
}

/* effet fade desktop uniquement */
@media (min-width: 768px) {
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
}

/* mobile optimisation */
@media (max-width: 768px) {
  .services-track {
    gap: 12px;
    padding-left: 10px;
  }

  .card {
    width: 70%;
  }
}
</style>
