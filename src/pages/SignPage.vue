<template>
  <q-page class="auth-page">
    <q-card class="auth-card">
      <q-tab-panels v-model="activeTab" animated>
        <!-- Formulaire de connexion -->
        <q-tab-panel name="signin">
          <h2 class="form-title">Welcome Back!</h2>
          <p class="form-subtitle">Please sign in to your account</p>
          <q-form @submit="handleSignIn" class="auth-form">
            <q-input
              v-model="signInForm.email"
              label="Email"
              type="email"
              outlined
              dense
              required
              class="q-mb-md"
            />
            <q-input
              v-model="signInForm.password"
              label="Password"
              type="password"
              outlined
              dense
              required
              class="q-mb-md"
            />
            <q-btn type="submit" label="Sign In" color="primary" class="full-width q-mt-md" />
            <div class="auth-link q-mt-md">
              <span>Don't have an account?</span>
              <q-btn flat label="Create one" color="primary" @click="activeTab = 'signup'" />
            </div>
          </q-form>
        </q-tab-panel>

        <!-- Formulaire d'inscription -->
        <q-tab-panel name="signup">
          <h2 class="form-title">Create an Account</h2>
          <p class="form-subtitle">Join us and start your journey</p>
          <q-form @submit="handleSignUp" class="auth-form">
            <q-input
              v-model="signUpForm.name"
              label="Name"
              type="text"
              outlined
              dense
              required
              class="q-mb-md"
            />
            <q-input
              v-model="signUpForm.email"
              label="Email"
              type="email"
              outlined
              dense
              required
              class="q-mb-md"
            />
            <q-input
              v-model="signUpForm.password"
              label="Password"
              type="password"
              outlined
              dense
              required
              class="q-mb-md"
            />
            <q-input
              v-model="signUpForm.confirmPassword"
              label="Confirm Password"
              type="password"
              outlined
              dense
              required
              class="q-mb-md"
            />
            <q-btn type="submit" label="Sign Up" color="primary" class="full-width q-mt-md" />
            <div class="auth-link q-mt-md">
              <span>Already have an account?</span>
              <q-btn flat label="Sign In" color="primary" @click="activeTab = 'signin'" />
            </div>
          </q-form>
        </q-tab-panel>
      </q-tab-panels>
    </q-card>
  </q-page>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const activeTab = ref('signin')

// Données pour le formulaire de connexion
const signInForm = ref({
  email: '',
  password: ''
})

// Données pour le formulaire d'inscription
const signUpForm = ref({
  name: '',
  email: '',
  password: '',
  confirmPassword: ''
})

// Gestion de la soumission du formulaire de connexion
const handleSignIn = () => {
  console.log('Sign In Data:', signInForm.value)
  // Ajoutez ici la logique pour gérer la connexion
}

// Gestion de la soumission du formulaire d'inscription
const handleSignUp = () => {
  console.log('Sign Up Data:', signUpForm.value)
  // Ajoutez ici la logique pour gérer l'inscription
}

// Masquer la barre de navigation
onMounted(() => {
  const navbar = document.querySelector('.q-header')
  if (navbar) {
    navbar.style.display = 'none'
  }
})
</script>

<style lang="scss">
.auth-page {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #6c63ff, #4caf50);
  padding: 20px;
}

.auth-card {
  width: 400px;
  max-width: 90%;
  padding: 30px;
  background: #ffffff;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  border-radius: 12px;
}

.form-title {
  font-size: 1.5rem;
  font-weight: bold;
  text-align: center;
  margin-bottom: 10px;
  color: #333;
}

.form-subtitle {
  font-size: 0.9rem;
  text-align: center;
  margin-bottom: 20px;
  color: #666;
}

.auth-form {
  display: flex;
  flex-direction: column;
}

.auth-link {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 16px;
  font-size: 0.9rem;
  color: #555;
}

.auth-link span {
  margin-right: 8px;
}

.full-width {
  width: 100%;
}

.q-mt-md {
  margin-top: 16px;
}
</style>
