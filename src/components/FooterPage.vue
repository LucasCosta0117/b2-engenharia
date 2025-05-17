<template>
  <v-footer class="footer-container d-flex flex-column align-start text-white">
    <v-col class="d-flex flex-column flex-sm-row justify-space-between">
      <div>
        <div>
          <img :src="logoComplete" alt="Logo B2 Engenharia e Construção" class="footer-logo"/>
          <div>
            <v-icon size="18" icon="mdi-phone-dial"></v-icon>
            <span class="text-caption"> +55 71 99114-2188</span>
          </div>
          <div>
            <v-icon size="18" icon="mdi-email"></v-icon>
            <span class="text-caption"> contato@b2engenhariaeconstrucao.com.br</span>
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
        <v-list class="d-flex flex-row bg-transparent">
          <v-list-item
            v-for="social in socialIcons"
            :key="social.icon"
          >
            <a :href="social.link" target="_blank">
              <v-icon size="32" :icon="social.icon" color="white"/>
            </a>
          </v-list-item>
        </v-list>
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
  height: 3.5rem;
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
