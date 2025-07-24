<template>
  <v-card class="card-services-container" elevation="3">
    <div class="card-services-text">
      <h3>{{ title }}</h3>
      <p class="section-paragraph">
        {{ paragraph }}
      </p>
    </div>
    <div class="card-services-img" :style="{ backgroundImage: `url(${require(`@/assets/image/card_serv/${imageName}`)})` }">
      <div class="overlay"></div>
    </div>
  </v-card>
</template>
<script>
export default {
  name: 'CardServices',
  props: {
    /**
     * Título para o card.
     */
    title: {
      type: String,
      required: true,
    },
    /**
     * Texto de descrição para o card.
     */
    paragraph: {
      type: String,
      required: true,
    },
    /**
     * Nome da imagem (salva em src/assets/image) para uso no background do card.
     */
    imageName: {
      type: String,
      required: true,
    }
  },
  data() {
    return {}
  }
}
</script>
<style scoped>
.card-services-container {
  display: flex;
  flex-direction: column;
}
.card-services-text {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 1rem;
}
.section-paragraph {
  font-size: 1rem;
}
.card-services-img {
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  max-width: 100%;
  height: 12rem;
  transition: transform 2s ease;
}
.card-services-img .overlay {
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.4);
  z-index: 1;
}
.card-services-container:hover .card-services-img {
  transform: scale(1.1);
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {

}
/**
 * Dispositivos médios
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .card-services-container {
    flex-direction: row;
    height: 15rem;
  }
  .card-services-text {
    width: 60%;
  }
  .card-services-img {
    width: 40%;
    height: inherit;
  }
  .card-services-container:hover .card-services-img {
    transform: scale(1.05);
  }
}

/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1400px) {

}
</style>