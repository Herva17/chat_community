<template>
  <q-page class="flex flex-center bg-grey-1">
    <div class="content-container q-pa-xl">
      <div class="text-center welcome-section q-mb-xl">
        <div class="title-container q-mb-lg">
          <h1 class="text-h2 text-weight-bold gradient-text q-mb-md">Communauté Chat</h1>
          <div class="subtitle-decorator"></div>
        </div>
        <p class="text-h6 text-grey-8 q-mb-xl description-text">
          Votre espace de communication privé et sécurisé pour vos communautés
        </p>
      </div>

      <div class="row q-col-gutter-xl justify-center">
        <!-- Carte Famille -->
        <div class="col-12 col-sm-4">
          <q-card class="custom-card" flat>
            <q-card-section class="text-center card-content">
              <div class="icon-container">
                <q-avatar size="100px" class="custom-avatar">
                  <q-icon name="family_restroom" size="50px" />
                </q-avatar>
              </div>
              <div class="text-h6 text-weight-bold q-mt-md q-mb-sm card-title">Espace Famille</div>
              <div class="text-subtitle2 text-grey-7">Restez connecté avec vos proches</div>
            </q-card-section>
          </q-card>
        </div>

        <!-- Carte Amis -->
        <div class="col-12 col-sm-4">
          <q-card class="custom-card" flat>
            <q-card-section class="text-center card-content">
              <div class="icon-container">
                <q-avatar size="100px" class="custom-avatar">
                  <q-icon name="groups" size="50px" />
                </q-avatar>
              </div>
              <div class="text-h6 text-weight-bold q-mt-md q-mb-sm card-title">Groupe d'Amis</div>
              <div class="text-subtitle2 text-grey-7">Partagez vos moments ensemble</div>
            </q-card-section>
          </q-card>
        </div>

        <!-- Carte Couple -->
        <div class="col-12 col-sm-4">
          <q-card class="custom-card" flat>
            <q-card-section class="text-center card-content">
              <div class="icon-container">
                <q-avatar size="100px" class="custom-avatar">
                  <q-icon name="favorite" size="50px" />
                </q-avatar>
              </div>
              <div class="text-h6 text-weight-bold q-mt-md q-mb-sm card-title">Espace Couple</div>
              <div class="text-subtitle2 text-grey-7">Un espace privé pour deux</div>
            </q-card-section>
          </q-card>
        </div>
      </div>

      <!-- Section des fonctionnalités -->
      <div class="features-section q-mt-xl q-pa-xl">
        <div class="text-h4 text-weight-bold text-center q-mb-xl features-title">
          Nos Fonctionnalités Principales
        </div>
        <div class="row q-col-gutter-xl justify-center">
          <div class="col-12 col-sm-6 col-md-3" v-for="(feature, index) in features" :key="index">
            <q-card class="feature-card" flat bordered>
              <q-card-section class="text-center">
                <div class="feature-icon-container">
                  <q-icon :name="feature.icon" size="40px" class="feature-icon" />
                </div>
                <div class="text-weight-bold q-mt-sm feature-title">{{ feature.title }}</div>
                <div class="text-caption q-mt-xs">{{ feature.caption }}</div>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup>
const features = [
  {
    icon: 'chat',
    title: 'Messagerie Instantanée',
    caption: 'Communication en temps réel'
  },
  {
    icon: 'security',
    title: 'Sécurité Maximale',
    caption: 'Cryptage de bout en bout'
  },
  {
    icon: 'photo_library',
    title: 'Partage de Médias',
    caption: 'Photos et vidéos'
  },
  {
    icon: 'event',
    title: "Organisation d'Événements",
    caption: 'Planification simplifiée'
  }
]
</script>

<style scoped>
:root {
  --primary-color: #6C63FF;
  --secondary-color: #3F3D56;
  --accent-color: #2F2E41;
  --gradient-start: #6C63FF;
  --gradient-end: #4CAF50;
}

.content-container {
  max-width: 1400px;
  width: 100%;
  margin: 0 auto;
}

.title-container {
  position: relative;
  display: inline-block;
}

.gradient-text {
  background: linear-gradient(45deg, var(--gradient-start), var(--gradient-end));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 800;
  letter-spacing: -1px;
}

.subtitle-decorator {
  width: 100px;
  height: 4px;
  background: linear-gradient(45deg, var(--gradient-start), var(--gradient-end));
  margin: 0 auto;
  border-radius: 2px;
}

.description-text {
  color: var(--secondary-color);
  max-width: 700px;
  margin: 2rem auto;
  font-weight: 400;
}

.custom-card {
  border-radius: 24px;
  background: white;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  height: 100%;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
}

.custom-avatar {
  background: linear-gradient(135deg, var(--gradient-start) 0%, var(--gradient-end) 100%);
  color: white;
  padding: 20px;
  transition: all 0.3s ease;
}

.icon-container {
  margin-bottom: 1.5rem;
}

.card-content {
  padding: 2rem;
}

.card-title {
  color: var(--accent-color);
  font-size: 1.5rem;
}

.custom-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 35px rgba(108, 99, 255, 0.2);
}

.features-section {
  background: white;
  border-radius: 30px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.05);
}

.features-title {
  color: var(--accent-color);
  position: relative;
  display: inline-block;
}

.feature-card {
  border-radius: 20px;
  transition: all 0.3s ease;
  border: 2px solid transparent !important;
  background: linear-gradient(white, white) padding-box,
              linear-gradient(45deg, var(--gradient-start), var(--gradient-end)) border-box;
}

.feature-icon-container {
  width: 80px;
  height: 80px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(108, 99, 255, 0.1), rgba(76, 175, 80, 0.1));
}

.feature-icon {
  color: var(--gradient-start);
}

.feature-title {
  color: var(--accent-color);
  font-size: 1.1rem;
  margin-top: 1rem;
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(108, 99, 255, 0.15);
  border-color: var(--gradient-start) !important;
}

/* Animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.custom-card, .feature-card {
  animation: fadeInUp 0.8s ease-out forwards;
}

/* Responsive adjustments */
@media (max-width: 600px) {
  .gradient-text {
    font-size: 2.5rem;
  }

  .features-section {
    padding: 1.5rem !important;
  }

  .content-container {
    padding: 1rem !important;
  }

  .custom-avatar {
    size: 80px;
  }
}
</style>
