<template>
  <section id="devis" class="quote">
    <h2>Demande de devis gratuit</h2>
    <p class="subtitle">Réponse rapide sous 24h – Intervention sur Saint-Sever et alentours</p>

    <form @submit.prevent="sendForm">
      <div class="grid">
        <input v-model="form.nom" type="text" placeholder="Nom / Prénom" required />
        <input v-model="form.telephone" type="tel" placeholder="Téléphone" required />
      </div>

      <input v-model="form.email" type="email" placeholder="Email" required />

      <div class="grid">
        <select v-model="form.service" required>
          <option disabled value="">Type de prestation</option>
          <option>Tonte de pelouse</option>
          <option>Taille de haies</option>
          <option>Débroussaillage</option>
          <option>Sciage d’arbre tombé</option>
          <option>Fendage de bois</option>
          <option>Entretien complet jardin</option>
        </select>

        <select v-model="form.urgence">
          <option value="normal">Intervention normale</option>
          <option value="urgent">Urgent (sous 48h)</option>
        </select>
      </div>

      <textarea
        v-model="form.message"
        placeholder="Décrivez votre besoin (surface, accès, contraintes...)"
        required
      ></textarea>

      <button type="submit">📩 Envoyer ma demande</button>

      <p v-if="sent" class="success">
        ✔ Votre demande a bien été envoyée, nous vous recontactons rapidement.
      </p>
    </form>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'

const sent = ref(false)

const form = reactive({
  nom: '',
  telephone: '',
  email: '',
  service: '',
  urgence: 'normal',
  message: '',
})

const sendForm = () => {
  // Ici tu pourras brancher Netlify Forms ou EmailJS
  console.log(form)

  sent.value = true

  setTimeout(() => {
    sent.value = false
  }, 5000)

  form.nom = ''
  form.telephone = ''
  form.email = ''
  form.service = ''
  form.urgence = 'normal'
  form.message = ''
}
</script>

<style scoped>
.quote {
  padding: 90px 20px;
  background: linear-gradient(180deg, #f7fdf7, #ffffff);
  text-align: center;
}

.subtitle {
  margin-top: 10px;
  color: #555;
  font-size: 1rem;
}

form {
  max-width: 700px;
  margin: 40px auto 0;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
}

input,
select,
textarea {
  padding: 15px;
  border-radius: 12px;
  border: 1px solid #ddd;
  font-size: 1rem;
  outline: none;
  transition: 0.2s;
}

input:focus,
select:focus,
textarea:focus {
  border-color: #2e7d32;
  box-shadow: 0 0 0 2px rgba(46, 125, 50, 0.2);
}

textarea {
  min-height: 140px;
  resize: vertical;
}

button {
  padding: 15px;
  border: none;
  border-radius: 12px;
  background: #2e7d32;
  color: white;
  font-size: 1.1rem;
  cursor: pointer;
  font-weight: bold;
  transition: 0.3s;
}

button:hover {
  background: #1b5e20;
  transform: translateY(-2px);
}

.success {
  color: #2e7d32;
  font-weight: bold;
  margin-top: 10px;
}

@media (max-width: 768px) {
  .grid {
    grid-template-columns: 1fr;
  }
}
</style>
