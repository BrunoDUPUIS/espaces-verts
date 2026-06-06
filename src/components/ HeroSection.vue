<template>
  <section class="hero">
    <div class="overlay">
      <h2>Votre artisan espaces verts à Saint-Sever</h2>
      <p>
        Entretien de jardins, tonte, débroussaillage, taille de haies et intervention sur arbres
        tombés.
      </p>

      <a href="#devis" class="btn">Demander un devis</a>
    </div>
  </section>
</template>

<style scoped>
.hero {
  height: 100vh;
  background-size: cover;
  background-position: center;
  animation: slideshow 24s infinite ease-in-out;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

@keyframes slideshow {
  0% {
    background-image: url('/public/images/bg1.jpg');
  }

  33% {
    background-image: url('/public/images/bg2.webp');
  }

  66% {
    background-image: url('/public/images/bg3.webp');
  }

  100% {
    background-image: url('/public/images/bg4.webp');
  }
}

.overlay {
  background: rgba(0, 0, 0, 0.45);
  padding: 40px;
  border-radius: 20px;
  text-align: center;
  color: white;
  max-width: 700px;
  margin: 20px;
  backdrop-filter: blur(3px);
}

h2 {
  font-size: 3rem;
  line-height: 1.2;
}

p {
  margin-top: 20px;
  font-size: 1.2rem;
}

.btn {
  display: inline-block;
  margin-top: 30px;
  padding: 15px 30px;
  background: #43a047;
  color: white;
  border-radius: 12px;
  text-decoration: none;
  font-weight: bold;
  transition: 0.3s;
}

.btn:hover {
  transform: translateY(-3px);
  background: #2e7d32;
}

@media (max-width: 768px) {
  .hero {
    padding: 20px;
  }

  .overlay {
    padding: 25px;
  }

  h2 {
    font-size: 2rem;
  }

  p {
    font-size: 1rem;
  }
}
</style>
