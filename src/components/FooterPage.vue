<template>
  <v-footer class="footer-container d-flex flex-column align-start text-white">
    <v-col class="d-flex flex-column flex-sm-row justify-space-between">
      <div>
        <div>
          <img :src="logoComplete" alt="Logo B2 Engenharia e Construção" class="footer-logo"/>
          <div>
            <v-icon size="18" icon="mdi-phone-dial"></v-icon>
            <span class="text-caption"> +55 71 99229-6560</span>
          </div>
          <div>
            <v-icon size="18" icon="mdi-email"></v-icon>
            <span class="text-caption"> financeiro@engenhariab2.com</span>
          </div>
          <div>
            <v-icon size="18" icon="mdi-map-marker"></v-icon>
            <span class="text-caption"> Vasco da Gama Plaza, Sala 1610, Salvador/BA</span>
          </div>
        </div>
      </div>
      <div class="d-flex flex-column align-center justify-center">
        <span class="d-none d-sm-flex follow-midia">
          Siga para saber mais
        </span>
        <SocialMidiaList></SocialMidiaList>
      </div>
    </v-col>
    <v-col class="footer-copyright">
      <p class="text-caption">
        © 2025 | B2 Engenharia & Construção | Todos os direitos reservados.
      </p>
      <p class="text-caption developed">
        Developed by <a :href="portfolioLink" target="_blank">Lucas Costa</a>
      </p>
    </v-col>
  </v-footer>
</template>
<script>
import SocialMidiaList from '@/components/SocialMidiaList.vue'

export default {
  name: 'FooterPage',
  components: {
    SocialMidiaList
  },
  data:() => ({
    logoComplete: require('@/assets/logo/logob2-cv.png'),
    portfolioLink: 'https://github.com/LucasCosta0117'
  })
}
</script>
<style scoped>
.footer-container {
  background: #000000;
  background: linear-gradient(145deg, rgba(0, 0, 0, 1) 0%, rgba(110, 13, 13, 1) 100%);
}
.footer-logo {
  height: 7rem;
  margin-left: 25%;
}
.footer-copyright {
  display: flex;
  flex-direction: column;
}
.follow-midia {
  font-size: 1rem;
  font-weight: 600;
  text-align: center;
  border-bottom: solid 1px rgba(245, 150, 8, 1);
}
.developed a {
  text-decoration: none;
  color: rgb(160, 160, 160);
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .footer-copyright {
    display: flex;
    gap: 2rem;
    flex-direction: row;
    justify-content: center;
  }
  .developed a {
    text-decoration: none;
    color: rgb(160, 160, 160);
    text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
  }
  .footer-logo {
    margin: 0rem;
  }
}
/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .caption-container {
    position: absolute;
    top: 50%;
    left: 12%;
    width: 36rem;
  }
  .caption-text {
    font-size: 3.5rem;
  }
}
</style>
