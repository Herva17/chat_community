<template>
  <q-layout view="hHh lpR fFf">
    <!-- En-tête (Header) -->
    <q-header elevated class="header-transparent">
      <q-toolbar class="header-content q-px-xl">
        <div class="logo-container">
          <span class="text-h5 text-weight-bold gradient-text">Communauté Chat</span>
        </div>

        <q-space />

        <!-- Menu de navigation -->
        <div class="gt-sm">
          <q-btn
            v-for="(item, index) in menuItems"
            :key="index"
            :to="item.link"
            flat
            no-caps
            class="menu-link q-px-md"
            :class="{ 'active-link': $route.path === item.link }"
          >
            {{ item.label }}
            <div class="link-indicator" />
          </q-btn>
        </div>

        <!-- Menu mobile -->
        <div class="lt-md">
          <q-btn
            flat
            dense
            round
            icon="menu"
            class="mobile-menu-btn"
            @click="toggleMobileMenu"
          />
        </div>
      </q-toolbar>
    </q-header>

    <!-- Menu mobile drawer -->
    <q-drawer
      v-model="mobileMenuOpen"
      side="right"
      bordered
      class="mobile-menu"
    >
      <q-list padding>
        <q-item
          v-for="(item, index) in menuItems"
          :key="index"
          :to="item.link"
          clickable
          v-ripple
          class="mobile-menu-item"
        >
          <q-item-section>
            {{ item.label }}
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <!-- Contenu principal -->
    <q-page-container>
      <router-view />
    </q-page-container>

    <!-- Footer -->
    
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)

const menuItems = [
  { label: 'Accueil', link: '/' },
  { label: 'À propos', link: '/about' },
  { label: 'Fonctionnalités', link: '/features' },
  { label: 'Contact', link: '/contact' }
]

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}
</script>

<style lang="scss">
:root {
  --primary-color: #6C63FF;
  --secondary-color: #4CAF50;
  --text-color: #3F3D56;
}

.header-transparent {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(0, 0, 0, 0.05);
}

.header-content {
  max-width: 1400px;
  margin: 0 auto;
  height: 80px;
}

.gradient-text {
  background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 700;
}

.menu-link {
  position: relative;
  color: var(--text-color);
  font-weight: 500;
  font-size: 1.05rem;
  padding: 8px 20px;
  margin: 0 5px;
  transition: all 0.3s ease;

  &:hover {
    color: var(--primary-color);

    .link-indicator {
      width: 100%;
      opacity: 1;
    }
  }

  &.active-link {
    color: var(--primary-color);

    .link-indicator {
      width: 100%;
      opacity: 1;
    }
  }

  .link-indicator {
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 0;
    height: 2px;
    background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
    transition: all 0.3s ease;
    opacity: 0;
  }
}

.mobile-menu {
  background: white;

  .mobile-menu-item {
    border-radius: 8px;
    margin: 4px 0;
    color: var(--text-color);
    font-weight: 500;

    &.q-router-link-active {
      color: var(--primary-color);
      background: rgba(108, 99, 255, 0.05);
    }
  }
}

.footer-content {
  max-width: 1400px;
  margin: 0 auto;
  border-top: 1px solid rgba(0, 0, 0, 0.05);
}

// Responsive
@media (max-width: 1024px) {
  .header-content {
    padding: 0 20px;
  }
}

@media (max-width: 600px) {
  .header-content {
    height: 70px;
  }
}
</style>
