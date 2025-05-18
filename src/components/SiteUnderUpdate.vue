<template>
  <v-container class="pt-16">
    <v-row>
      <v-col col="12">
        <v-img
          :src="logoOffice"
          class="update-logo"
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col col="12" class="update-title">
        <p>
          Site em Atualização!
        </p>
      </v-col>
    </v-row>
    <v-row class="d-flex justify-center">
      <v-col col="12" class="update-subtitle">
        <p>
          Estamos trabalhando em um espaço novo, moderno e elegante para melhor te atender.
        </p>
      </v-col>
    </v-row>
    <v-row>
      <v-col col="12" class="d-flex justify-center mb-8">
        <v-img 
          :src="excavatorGif"
          class="update-gif"
        />
      </v-col>
    </v-row>
    <v-row class="d-flex flex-column">
      <v-col col="12" class="d-flex justify-center">
        <span class="follow-midia">
          Siga para saber mais
        </span>
      </v-col>
      <v-col col="12" class="d-flex justify-center text-center">
        <v-list class="d-flex flex-row">
          <v-list-item
            v-for="social in socialIcons"
            :key="social.icon"
          >
            <a :href="social.link" target="_blank">
              <v-icon size="40" :icon="social.icon" color="black"/>
            </a>
          </v-list-item>
        </v-list>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  name: 'SiteUnderUpdate',
  data: () => ({
    logoOffice: require('@/assets/logo/logob2-o.png'),
    excavatorGif: require('@/assets/gif/excavator.gif'),
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
    ],

  }),
}
</script>
<style scoped>
.update-logo {
  height: 7rem;
}
.update-title {
  font-size: 1.1em;
  font-weight: 800;
  text-align: center;
  text-transform: uppercase;
  text-shadow: lightgray 1px 1px 3px;
  color: rgb(90, 90, 90);
}
.update-subtitle {
  font-size: 0.8rem;
  font-weight: 500;
  text-align: center;
  color: gray;
}
.update-gif {
  height: 7rem;
}
.follow-midia {
  font-size: 1rem;
  font-weight: 600;
  text-align: center;
  color: rgb(60, 60, 60);
  border-bottom: solid 1px rgba(245, 150, 8, 1);
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .update-logo {
    height: 8rem;
  }
  .update-title {
    font-size: 1.2em;
  }
  .update-subtitle {
    max-width: 450px;
  }
  .update-gif {
    height: 8rem;
  }
}
/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .update-logo {
    height: 10rem;
  }
  .update-title {
    font-size: 1.3em;
  }
}
</style>