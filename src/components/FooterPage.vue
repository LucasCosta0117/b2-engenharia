<template>
  <v-footer class="footer-container d-flex flex-column">
    <v-col>
      <img :src="logoComplete" alt="Logo B2 Engenharia e Construção" class="footer-logo"/>
    </v-col>
    <v-col class="text-white">
      <p>
        Tel.:
      </p>
      <p>
        e-mail.:
      </p>
    </v-col>
    <v-col>
      <ul class="d-flex flex-row ga-8">
        <li
          v-for="social in socialIcons"
          :key="social.icon"
        >
          <a :href="social.link" target="_blank">
            <v-icon size="32" :icon="social.icon" color="white"/>
          </a>
        </li>
      </ul>
    </v-col>
    <v-col>
      <p class="text-white text-caption">
        © B2 Engenharia & Construção 2025 |
      </p>
      <p class="text-white text-caption">
        Todos os direitos reservados.
      </p>
      <p class="text-white text-caption">
        Developed by <a :href="portfolioLink" target="_blank">Lucas Costa</a>
      </p>
    </v-col>
  </v-footer>
</template>
<script>
export default {
  name: 'FooterPage',
  data:() => ({
    logoComplete: require('@/assets/logo/logob2-c.png'),
    portfolioLink: 'https://github.com/LucasCosta0117',
    socialIcons: [
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
  }),
}
</script>
<style scoped>
.footer-container {
  background: #000000;
  background: linear-gradient(145deg, rgba(0, 0, 0, 1) 0%, rgba(110, 13, 13, 1) 100%);
}
.footer-logo {
  height: 10rem;
}
</style>
