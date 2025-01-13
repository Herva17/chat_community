<template>
  <!-- Footer Section -->
  <footer class="footer-section q-pt-xl">
    <div class="content-container">
      <div class="row q-col-gutter-md">

        <!-- Logo et Description -->
        <div class="col-12 col-md-4 q-pb-md text-center text-md-left">
          <div class="text-h5 text-weight-bold gradient-text q-mb-sm">Communauté Chat</div>
          <p class="text-body1 text-grey-7 q-mb-sm">
            Votre plateforme de communication sécurisée pour rester connecté avec vos proches.
          </p>
          <div class="social-links q-gutter-sm text-center">
            <q-btn flat round color="primary" aria-label="Facebook" size="sm">
              <q-icon name="fa fa-facebook" />
            </q-btn>
            <q-btn flat round color="primary" aria-label="Twitter" size="sm">
              <q-icon name="fa fa-twitter" />
            </q-btn>
            <q-btn flat round color="primary" aria-label="Instagram" size="sm">
              <q-icon name="fa fa-instagram" />
            </q-btn>
            <q-btn flat round color="primary" aria-label="LinkedIn" size="sm">
              <q-icon name="fa fa-linkedin" />
            </q-btn>
          </div>
        </div>

        <!-- Services -->
        <div class="col-12 col-md-2 q-pb-md text-center text-md-left">
          <div class="text-subtitle1 text-weight-bold q-mb-sm">Services</div>
          <q-list dense padding class="q-pa-none">
            <q-item clickable v-ripple>
              <q-item-section>Espace Famille</q-item-section>
            </q-item>
            <q-item clickable v-ripple>
              <q-item-section>Groupe d'Amis</q-item-section>
            </q-item>
            <q-item clickable v-ripple>
              <q-item-section>Espace Couple</q-item-section>
            </q-item>
            <q-item clickable v-ripple>
              <q-item-section>Support</q-item-section>
            </q-item>
          </q-list>
        </div>

        <!-- Contact -->
        <div class="col-12 col-md-4 q-pb-md text-center text-md-left">
          <div class="text-subtitle1 text-weight-bold q-mb-sm">Contactez-nous</div>
          <q-list dense padding class="q-pa-none">
            <q-item>
              <q-item-section avatar>
                <q-icon name="fa fa-map-marker-alt" color="primary" />
              </q-item-section>
              <q-item-section>123 Rue de la Communication, 75000 Paris</q-item-section>
            </q-item>
            <q-item>
              <q-item-section avatar>
                <q-icon name="fa fa-envelope" color="primary" />
              </q-item-section>
              <q-item-section>contact@communautechat.com</q-item-section>
            </q-item>
            <q-item>
              <q-item-section avatar>
                <q-icon name="fa fa-phone" color="primary" />
              </q-item-section>
              <q-item-section>+33 1 23 45 67 89</q-item-section>
            </q-item>
          </q-list>
        </div>

      </div>

      <!-- Copyright -->
      <q-separator class="q-my-lg" />
      <div class="row items-center justify-between q-py-sm footer-bottom">
        <div class="text-caption text-grey-7">
          © {{ currentYear }} Communauté Chat. Tous droits réservés.
        </div>
        <div class="row q-gutter-sm text-caption text-grey-7">
          <a href="#" class="text-grey-7">Conditions d'utilisation</a>
          <span>|</span>
          <a href="#" class="text-grey-7">Politique de confidentialité</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
    };
  },
};
</script>

<style scoped>
/* Ajoutez ici des styles personnalisés pour votre footer si nécessaire */
.footer-section {
  background-color: #090404; /* Exemple de couleur de fond */
  padding: 15px; /* Moins de padding pour réduire la hauteur */
  color: #817474;
}

.text-h5 {
  font-size: 1.25rem; /* Ajustez la taille du texte */
  color: #817474;
}

.text-body1 {
  font-size: 0.9rem; /* Taille de texte plus petite pour économiser de l'espace */
  color: #817474;
}

.text-subtitle1 {
  font-size: 1rem; /* Taille pour les sous-titres */
  font-weight: bold;
  color: #f1e5e5;
}

.q-gutter-sm {
  gap: 5px; /* Espacement réduit pour les boutons sociaux */
}

.footer-bottom {
  font-size: 0.75rem;
  color: #817474;
} /* Taille plus petite pour le bas de page */

@media (max-width: 600px) {
  .footer-section {
    padding: 10px;
  }

  .q-btn {
    margin: 3px; /* Espacement réduit entre les icônes sociales */
  }

  .text-h5 {
    font-size: 1.2rem; /* Taille plus petite du titre sur mobile */
  }

  .text-body1 {
    font-size: 0.875rem; /* Réduire la taille du texte sur mobile */
  }

  .text-subtitle1 {
    font-size: 0.95rem; /* Sous-titres un peu plus petits */
  }

  .footer-bottom {
    font-size: 0.75rem;
  }
}
</style>
