<template>
  <div class="admin">
    <div v-if="!logged">
      <h1>Administration</h1>

      <input v-model="password" type="password" placeholder="Mot de passe" />

      <button @click="login">Connexion</button>
    </div>

    <div v-else>
      <h1>Panneau Admin</h1>

      <label>Nom entreprise</label>
      <input v-model="site.nomEntreprise" />

      <label>Téléphone</label>
      <input v-model="site.telephone" />

      <label>Email</label>
      <input v-model="site.email" />

      <label>Bandeau</label>
      <textarea v-model="site.bandeau"></textarea>

      <button @click="save">Sauvegarder</button>

      <p v-if="saved" class="success">✔ Modifications enregistrées</p>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive, onMounted } from 'vue'

const password = ref('')
const logged = ref(false)
const saved = ref(false)

const ADMIN_PASSWORD = 'pere2026'

const site = reactive({
  nomEntreprise: '',
  telephone: '',
  email: '',
  bandeau: '',
})

const login = () => {
  if (password.value === ADMIN_PASSWORD) {
    logged.value = true
    loadData()
  } else {
    alert('Mot de passe incorrect')
  }
}

const loadData = async () => {
  const response = await fetch('/data/site.json')
  const data = await response.json()

  Object.assign(site, data)
}

const save = () => {
  // ⚠ ici on simulera
  // vraie sauvegarde expliquée plus bas

  console.log(JSON.stringify(site, null, 2))

  saved.value = true

  setTimeout(() => {
    saved.value = false
  }, 3000)
}
</script>

<style scoped>
.admin {
  max-width: 700px;
  margin: auto;
  padding: 40px 20px;

  display: flex;
  flex-direction: column;
  gap: 15px;
}

input,
textarea {
  padding: 14px;
  border-radius: 10px;
  border: 1px solid #ccc;
}

button {
  padding: 14px;
  border: none;
  background: #2e7d32;
  color: white;
  border-radius: 10px;
  cursor: pointer;
}

.success {
  color: green;
  font-weight: bold;
}
</style>
