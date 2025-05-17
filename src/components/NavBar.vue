<template>
  <v-app-bar
    v-if="!drawer"
    flat
    :height="[scrolled ? 64 : 80 ]"
    :class="[scrolled ? 'onRoll-nav-bar' : 'onTop-nav-bar']"
  >
    <v-app-bar-nav-icon
      @click="drawer = !drawer"
      class="d-md-none text-white"
    />

    <router-link :to="linkHome.to" class="ml-8 d-md-none">
      <img :src="logoSimple" alt="Logo B2 Engenharia e Construção" class="navbar-logo-s"/>
    </router-link>
    <router-link :to="linkHome.to" class="ml-8 d-none d-md-flex">
      <img :src="logoComplete" alt="Logo B2 Engenharia e Construção" class="navbar-logo-c mr-16"/>
    </router-link>
    
    <v-btn
      v-for="link in linksNavbar"
      :key="link.to"
      :to="link.to"
      text
      class="d-none d-md-flex text-white btn-nav-bar"
      :class="{ 'btn-nav-bar-active': $route.path === link.to }"
      height="100%"
    >
      {{ link.label }}
    </v-btn>
    <v-spacer></v-spacer>
    <v-btn
      :to="linkContact.to"
      text
      class="d-md-flex mr-2 text-white btn-contact"
    >
      {{ linkContact.label }}
    </v-btn>
  </v-app-bar>

  <v-navigation-drawer
    v-model="drawer"
    temporary
    class="d-sm-md-none onRoll-nav-bar"
  >
    <v-list class="mb-16">
      <router-link :to="linkHome.to" class="ml-4 d-md-none">
        <img :src="logoSimple" alt="Logo B2 Engenharia e Construção" class="navbar-logo-s"/>
      </router-link>
      <v-list-item
        v-for="link in linksNavbar"
        :key="link.to"
        :to="link.to"
        @click="drawer = false"
        :class="{ 'btn-drawer-bar-active': $route.path === link.to }"
        link
      >
        <v-list-item-title class="text-white">{{ link.label }}</v-list-item-title>
      </v-list-item>
    </v-list>
    <v-btn
      :to="linkContact.to"
      text
      class="d-md-flex ml-4 mb-16 "
    >
      {{ linkContact.label }}
    </v-btn>
    <v-list class="d-flex flex-row">
      <v-list-item
        v-for="social in socialIcons"
        :key="social.icon"
      >
        <a :href="social.link" target="_blank">
          <v-icon size="32" :icon="social.icon" color="white"/>
        </a>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const drawer = ref(false)
const scrolled = ref(false)

const logoSimple = require('@/assets/logo/logob2-s.png')
const logoComplete = require('@/assets/logo/logob2-c.png')

const linksNavbar = [
  { to: '/', label: 'Início' },
  { to: '/about', label: 'Quem somos' },
  { to: '/services', label: 'Serviços' },
  { to: '/partners', label: 'Parceiros' },
  { to: '/gallery', label: 'Portifólio' }
]
const linkHome = {
  to: '/', label: 'Início'
}
const linkContact = {
  to: '/contact', label: 'Fale Conosco'
}

const socialIcons= [
  {
    icon: 'mdi-instagram',
    alt: 'Logo do Instagram',
    link: 'https://www.instagram.com/b2'
  },
  {
    icon: 'mdi-facebook',
    alt: 'Logo do Facebook',
    link: 'https://www.facebook.com/b2'
  },
  {
    icon: 'mdi-whatsapp',
    alt: 'Logo do Whatsapp',
    link: 'https://wa.me/+557199999999999'
  }
]

// Detectar scroll
const handleScroll = () => {
  scrolled.value = window.scrollY > 80
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

</script>
<style scoped>
.onTop-nav-bar,
.onRoll-nav-bar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
}
.onTop-nav-bar {
  background: linear-gradient(180deg,rgba(0, 0, 0, 0.5) 0%, rgba(235, 235, 235, 0.3) 100%);
  border-bottom: solid 1px rgb(255, 255, 255);
}
.onRoll-nav-bar {
  background: rgba(85, 4, 4, 1);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.4);
  transition: background 0.3s ease-out;
  transition: 0.2s ease-in-out;
}
.navbar-logo-s {
  max-width: 2.5rem;
}
.navbar-logo-c {
  max-width: 10rem;
}
.btn-contact {
  border: solid 1px white;
  background-color: rgba(245, 150, 8, 1);
}
.btn-contact:hover {
  scale: 0.98;
}
.btn-nav-bar:hover {
  border-top: solid 2px rgba(245, 150, 8, 1);
  border-radius: 0px;
}
.btn-nav-bar-active {
  border-top: solid 2px rgba(245, 150, 8, 1);
  border-radius: 0px;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.8);
  font-weight: 600;
}
.btn-drawer-bar-active {
  text-shadow: 1px 2px 5px rgba(0, 0, 0, 0.6);
}

</style>
