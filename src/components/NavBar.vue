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
      <img :src="logoComplete" alt="Logo B2 Engenharia e Construção" class="navbar-logo-c"/>
    </router-link>

    <v-btn
      v-for="link in linksNavbar"
      :key="link.to"
      :to="link.to"
      text
      class="d-none d-md-flex text-white"
    >
      {{ link.label }}
    </v-btn>
    <v-spacer></v-spacer>
    <v-btn
    :to="linkContact.to"
      text
      class="d-md-flex mr-2 text-white"
    >
      {{ linkContact.label }}
    </v-btn>
  </v-app-bar>

  <v-navigation-drawer
    v-model="drawer"
    temporary
    class="d-sm-md-none onRoll-nav-bar"
  >
    <v-list>
      <v-list-item
        v-for="link in linksNavbar"
        :key="link.to"
        :to="link.to"
        @click="drawer = false"
        link
      >
        <v-list-item-title class="text-white">{{ link.label }}</v-list-item-title>
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
  { to: '/sobre', label: 'Sobre' },
  { to: '/galeria', label: 'Galeria' }
]
const linkHome = {
  to: '/', label: 'Início'
}
const linkContact = {
  to: '/contact', label: 'Fale Conosco'
}

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
}
.navbar-logo-s {
  max-width: 2.5rem;
}
.navbar-logo-c {
  max-width: 10rem;
}
</style>
