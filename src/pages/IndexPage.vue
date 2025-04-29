<template>

    <q-page class="home-page">
      <!-- Section Héro -->
      <section class="hero-section" style="margin-top: -100px;">
        <div class="content-container">
          <div class="row items-center">
            <div class="col-12 col-md-6 text-left">
              <h1 class="text-h2 text-weight-bold gradient-text q-mb-md">
                Connectez-vous avec vos proches
              </h1>
              <p class="text-h6 text-grey-8 q-mb-xl description-text">
                Communauté Chat vous offre un espace de communication privé et sécurisé pour tous vos groupes : famille, amis et plus encore.
              </p>
              <div class="q-gutter-md">
                <q-btn
                  unelevated
                  size="lg"
                  class="get-started-btn"
                  label="Commencer maintenant"
                />
                <q-btn
                  outline
                  size="lg"
                  class="demo-btn"
                  label="Voir la démo"
                  icon="play_circle"
                />
              </div>
            </div>
            <div class="col-12 col-md-6">
              <img src="img/Group Chat-bro.svg" class="hero-image" alt="Communication illustration">
            </div>
          </div>
        </div>
      </section>

      <!-- Section Statistiques -->
      <section class="stats-section q-py-xl">
        <div class="content-container">
          <div class="row q-col-gutter-lg text-center">
            <div class="col-12 col-sm-4">
              <div class="stat-card">
                <div class="text-h3 text-weight-bold gradient-text">10K+</div>
                <div class="text-subtitle1">Utilisateurs actifs</div>
              </div>
            </div>
            <div class="col-12 col-sm-4">
              <div class="stat-card">
                <div class="text-h3 text-weight-bold gradient-text">5M+</div>
                <div class="text-subtitle1">Messages échangés</div>
              </div>
            </div>
            <div class="col-12 col-sm-4">
              <div class="stat-card">
                <div class="text-h3 text-weight-bold gradient-text">99.9%</div>
                <div class="text-subtitle1">Taux de satisfaction</div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Section Espaces -->
      <section class="spaces-section q-py-xl">
        <div class="content-container">
          <h2 class="text-h3 text-center text-weight-bold q-mb-xl">
            Des espaces adaptés à vos besoins
          </h2>
          <div class="row q-col-gutter-xl justify-center">
            <div class="col-12 col-sm-4" v-for="(space, index) in spaces" :key="index">
              <q-card class="space-card" flat>
                <q-card-section class="text-center">
                  <q-avatar size="80px" :class="space.class">
                    <q-icon :name="space.icon" size="40px" />
                  </q-avatar>
                  <h3 class="text-h5 q-mt-md q-mb-sm">{{ space.title }}</h3>
                  <p class="text-body1 text-grey-7">{{ space.description }}</p>
                  <q-btn
                    flat
                    color="primary"
                    :label="'En savoir plus sur ' + space.title"
                    class="q-mt-md"
                  />
                </q-card-section>
              </q-card>
            </div>
          </div>
        </div>
      </section>

      <!-- Section Fonctionnalités -->
      <section class="features-section q-py-xl">
        <div class="content-container">
          <h2 class="text-h3 text-center text-weight-bold q-mb-xl">
            Fonctionnalités principales
          </h2>
          <div class="row q-col-gutter-xl">
            <div class="col-12 col-sm-6 col-md-3" v-for="feature in features" :key="feature.title">
              <q-card class="feature-card" flat bordered>
                <q-card-section class="text-center">
                  <div class="feature-icon-container">
                    <q-icon :name="feature.icon" size="40px" class="feature-icon" />
                  </div>
                  <h4 class="text-h6 q-mt-md">{{ feature.title }}</h4>
                  <p class="text-body2 q-mt-sm text-grey-7">{{ feature.caption }}</p>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </div>
      </section>

      <!-- Section CTA -->
      <section class="cta-section q-py-xl text-center">
        <div class="content-container">
          <h2 class="text-h3 text-weight-bold q-mb-md">Prêt à rejoindre la communauté ?</h2>
          <p class="text-h6 text-grey-8 q-mb-xl">
            Commencez dès aujourd'hui et découvrez une nouvelle façon de communiquer
          </p>
          <q-btn
            unelevated
            size="lg"
            class="get-started-btn"
            label="Créer un compte gratuitement"
          />
        </div>
      </section>
    </q-page>
  <FooterVue/>
</template>

<script setup>
import MainLayout from 'src/layouts/FooterVue.vue';

const spaces = [
  {
    icon: 'family_restroom',
    title: 'Espace Famille',
    description: 'Gardez le contact avec vos proches et partagez les moments importants de la vie familiale.',
    class: 'bg-purple-2'
  },
  {
    icon: 'groups',
    title: 'Groupe d\'Amis',
    description: 'Organisez vos sorties et restez connectés avec votre cercle d\'amis.',
    class: 'bg-green-2'
  },
  {
    icon: 'favorite',
    title: 'Espace Couple',
    description: 'Un espace privé et intime pour partager vos moments à deux.',
    class: 'bg-pink-2'
  }
];

const features = [
  {
    icon: 'chat',
    title: 'Messagerie Instantanée',
    caption: 'Communication en temps réel avec tous vos groupes'
  },
  {
    icon: 'security',
    title: 'Sécurité Maximale',
    caption: 'Vos conversations sont protégées de bout en bout'
  },
  {
    icon: 'photo_library',
    title: 'Partage de Médias',
    caption: 'Partagez facilement photos et vidéos'
  },
  {
    icon: 'event',
    title: 'Organisation',
    caption: 'Planifiez vos événements simplement'
  }
];
</script>

<style scoped>
.home-page {
  background: #f8f9fa;
}

.hero-section {
  background: linear-gradient(135deg, rgba(108, 99, 255, 0.1), rgba(76, 175, 80, 0.1));
  padding: 100px 0;
  position: relative;
  overflow: hidden;
}

.content-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.hero-image {
  max-width: 100%;
  height: auto;
  animation: float 6s ease-in-out infinite;
}

.get-started-btn {
  background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
  color: white;
  font-weight: 500;
  padding: 12px 32px;
}

.demo-btn {
  color: var(--primary-color);
  border-color: var(--primary-color);
}

.stat-card {
  padding: 30px;
  background: white;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.stat-card:hover {
  transform: translateY(-5px);
}

.space-card {
  padding: 40px 20px;
  border-radius: 20px;
  background: white;
  transition: all 0.3s ease;
  height: 100%;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
}

.space-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 30px rgba(108, 99, 255, 0.15);
}

.feature-card {
  padding: 30px;
  border-radius: 16px;
  height: 100%;
  transition: all 0.3s ease;
}

.cta-section {
  background: linear-gradient(135deg, rgba(108, 99, 255, 0.1), rgba(76, 175, 80, 0.1));
  padding: 80px 0;
}

@keyframes float {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(0px);
  }
}

@media (max-width: 600px) {
  .hero-section {
    padding: 60px 0;
  }

  .hero-image {
    margin-top: 40px;
  }
}
</style>