<template>
  <section id="avis" class="reviews">
    <h2>Avis Clients</h2>

    <div class="review-list">
      <div class="review">
        ⭐⭐⭐⭐⭐
        <p><strong>Jésus</strong> : Travail impeccable et rapide ! Bravo à François et Mathias</p>
      </div>

      <div class="review">
        ⭐⭐⭐⭐⭐
        <p><strong>Marie</strong> : Très professionnel et sympathique. Super équipe !</p>
      </div>

      <div class="review">
        ⭐⭐⭐⭐⭐
        <p>
          <strong>Joseph</strong> : Jardin parfaitement entretenu, je recommande. Merci à François
          pour le repas de ce midi !
        </p>
      </div>

      <div class="review">
        ⭐⭐⭐⭐⭐
        <p><strong>Bruno</strong> : Intervention rapide après une tempête, très efficace.</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.reviews {
  padding: 80px 20px;
  text-align: center;
  background: white;
}

.review-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin-top: 40px;
}

.review {
  background: #f1f8e9;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  transition: transform 0.2s ease;
}

.review:hover {
  transform: translateY(-5px);
}

.review p {
  margin-top: 10px;
  font-size: 1rem;
}
</style>
