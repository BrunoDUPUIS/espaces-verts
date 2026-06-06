<template>
  <div class="top-banner">
    <div class="scroll-text">
      🌿 Tonte de pelouse • Débroussaillage • Taille de haies • Sciage et fendage d’arbres •
      Intervention rapide • Devis gratuit 🌿
    </div>
  </div>

  <header class="header">
    <div class="logo">
      <span class="logo-icon">🌿</span>
      <span class="logo-text">Les Jardins de Péré</span>
    </div>

    <nav>
      <a href="#services">Services</a>
      <a href="#avis">Avis</a>
      <a href="#devis">Devis</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>
</template>

<style scoped>
.top-banner {
  background: #2e7d32;
  color: white;
  overflow: hidden;
  white-space: nowrap;
  padding: 10px 0;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
}

.scroll-text {
  display: inline-block;
  padding-left: 100%;
  animation: scroll 20s linear infinite;
  font-weight: bold;
}

@keyframes scroll {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-100%);
  }
}

.header {
  margin-top: 50px;
  padding: 20px;
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(6px);
  color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

nav {
  display: flex;
  gap: 20px;
}

nav a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

@media (max-width: 768px) {
  .header {
    flex-direction: column;
    text-align: center;
    gap: 15px;
  }

  nav {
    flex-wrap: wrap;
    justify-content: center;
  }
}
.logo-title {
  font-size: 2.2rem;
  font-weight: 900;
  color: #ffffff;
  letter-spacing: 1px;

  /* Effet visibilité forte */
  text-shadow:
    0 2px 5px rgba(0, 0, 0, 0.8),
    0 0 10px rgba(0, 0, 0, 0.6);

  /* Petit effet moderne */
  padding: 5px 10px;
  border-radius: 10px;

  /* Dégradé subtil */
  background: linear-gradient(90deg, rgba(46, 125, 50, 0.35), rgba(0, 0, 0, 0));

  display: inline-block;
}

/* Responsive mobile */
@media (max-width: 768px) {
  .logo-title {
    font-size: 1.6rem;
    text-align: center;
  }
}
.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 6px 12px;
  border-radius: 12px;

  /* Fond discret premium */
  background: rgba(0, 0, 0, 0.25);
  backdrop-filter: blur(6px);

  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

.logo-icon {
  font-size: 1.8rem;
  filter: drop-shadow(0 2px 3px rgba(0, 0, 0, 0.5));
}

.logo-text {
  font-size: 1.6rem;
  font-weight: 800;
  color: white;
  letter-spacing: 0.5px;

  /* lisibilité sur images */
  text-shadow: 0 2px 6px rgba(0, 0, 0, 0.8);
}

/* Effet hover subtil */
.logo:hover {
  transform: scale(1.02);
  transition: 0.3s ease;
}

/* Responsive mobile */
@media (max-width: 768px) {
  .logo-text {
    font-size: 1.2rem;
  }

  .logo-icon {
    font-size: 1.5rem;
  }
}
</style>
