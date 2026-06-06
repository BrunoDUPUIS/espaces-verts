<template>
  <div class="site">
    <!-- BANDEAU DÉFILANT -->
    <div class="top-banner">
      <div class="scrolling-text">
        🌿 Les jardins de Péré • Tonte • Débroussaillage • Taille de haies • Sciage et fendage de
        vos arbres tombés • Intervention rapide • Devis gratuit • 06 66 68 55 58 • Avec évacuation
        des déchets !
      </div>
    </div>

    <!-- HERO -->
    <header class="hero" :style="{ backgroundImage: `url(${backgrounds[currentBg]})` }">
      <div class="overlay">
        <h1>Les jardins de Péré</h1>

        <p>Entretien et aménagement de vos espaces verts</p>

        <div class="hero-buttons">
          <a href="#devis" class="btn"> Demander un devis </a>

          <a href="tel:0666685558" class="btn secondary"> Appeler maintenant </a>
        </div>
      </div>
    </header>

    <!-- SERVICES -->
    <section class="services">
      <h2>Nos Services</h2>

      <div class="cards">
        <div class="card">
          <h3>🌱 Tonte de pelouse</h3>
          <p>Entretien régulier ou ponctuel de vos espaces verts.</p>
        </div>

        <div class="card">
          <h3>🔥 Débroussaillage</h3>
          <p>Nettoyage de terrains, jardins et grandes surfaces.</p>
        </div>

        <div class="card">
          <h3>✂️ Taille de haies</h3>
          <p>Taille propre avec évacuation des déchets verts.</p>
        </div>

        <div class="card">
          <h3>🪓 Sciage & fendage</h3>
          <p>Découpe et fendage d’arbres tombés ou bois.</p>
        </div>
      </div>
    </section>

    <!-- AVIS -->
    <section class="reviews">
      <h2>Avis Clients</h2>

      <div class="review-list">
        <div class="review">
          <p>
            "Travail sérieux et très propre, je recommande. Un granbd merci à François et Mathias
            une super équipe"
          </p>

          <strong>⭐⭐⭐⭐⭐ - Jésus.</strong>
        </div>

        <div class="review">
          <p>"Intervention rapide pour un terrain envahi. Bravo à François et son équipe"</p>

          <strong>⭐⭐⭐⭐⭐ - Marie.</strong>
        </div>

        <div class="review">
          <p>"Très professionnel et sympathique."</p>

          <strong>⭐⭐⭐⭐⭐ - Joseph.</strong>
        </div>
      </div>
    </section>

    <!-- DEVIS -->
    <section class="quote" id="devis">
      <h2>Demande de devis</h2>

      <form @submit.prevent="sendForm">
        <input type="text" placeholder="Votre nom" required />

        <input type="tel" placeholder="Téléphone" required />

        <input type="email" placeholder="Adresse email" required />

        <textarea rows="6" placeholder="Décrivez votre besoin..." required></textarea>

        <button type="submit">Envoyer la demande</button>
      </form>
    </section>

    <!-- GOOGLE MAPS -->
    <section class="map-section">
      <h2>Nous trouver</h2>
      <div class="map-container">
        <iframe
          src="https://www.google.com/maps?q=11+avenue+du+General+de+Gaulle+40500+Saint-Sever&output=embed"
          allowfullscreen=""
          loading="lazy"
        ></iframe>
      </div>
    </section>

    <!-- CONTACT -->
    <footer>
      <h3>Contact</h3>

      <p>📞 06 66 68 55 58</p>

      <p>📧 contact@lesjardinsdepere.fr</p>

      <p>
        📍 11 avenue du Général de Gaulle
        <br />
        40500 Saint-Sever
      </p>

      <p class="copyright">© 2026 Les jardins de Péré - Réalisation Bruno DUPUIS</p>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const backgrounds = [
  '/images/bg1.jpg',
  '/images/bg2.webp',
  '/images/bg3.webp',
  '/images/bg4.webp',
  '/images/bg5.webp',
]

const currentBg = ref(0)

onMounted(() => {
  setInterval(() => {
    currentBg.value = (currentBg.value + 1) % backgrounds.length
  }, 7000)
})

const sendForm = () => {
  alert('Votre demande a bien été envoyée !')
}
</script>
