<template>
  <div class="card-container">
    <div class="card-title">
      {{ title }}
    </div>
    <div class="card-info">
      <div class="card-thumb">
        <v-img cover class="card-thumb-img" :src="thumbUrl"/>
      </div>
      <div>
        <div class="card-features">
          <div>
            <div class="feature-item">
              <v-icon size="18" icon="mdi-bed-king"></v-icon>
              {{ feature.bedrooms }}
            </div>
            <div class="feature-item">
              <v-icon size="18" icon="mdi-ruler-square"></v-icon>
              {{ feature.area }}
            </div>
          </div>
          <div>
            <div class="feature-item">
              <v-icon size="18" icon="mdi-map-marker"></v-icon>
              {{ feature.city }}
            </div>
            <div class="feature-item">
              <v-icon size="18" icon="mdi-calendar-month"></v-icon>
              {{ feature.launch }}
            </div>
          </div>
        </div>
        <a v-if="website" class="card-link" :href="website" target="_blank">
          <span>Visite o site</span>
          <i class="mdi mdi-page-last"></i>
        </a>
      </div>
    </div>
  </div>
</template>
<script>
/**
 * Card que expoem um item do portifólio.
 */
export default {
  name: 'CardGallery',
  props: {
    /**
     * Nome do empreendimento
     */
    title: {
      type: String,
      require: true,
      default: 'Employment'
    },
    /**
     * Foto da capa do card
     */
    thumbUrl: {
      type: String,
      require: true,
      default: require('@/assets/image/gallery-header.webp')
    },
    /**
     * Características do empreendimento
     */
    feature: {
      type: Object,
      require: true,
      default: () => {
        return {
          bedrooms: '2 quartos',
          area: '50m²',
          city: 'Salvador - BA',
          launch: '2025'
        }
      }
    },
    /**
     * Acesso ao website do empreendimento
     */
    website: {
      type: String,
      require: false
    }
  },
  data() {
    return {}
  }
}
</script>
<style scoped>
.card-container {
  display: flex;
  width: 100%;
  height: 25rem;
  border-radius: 1rem;
}
.card-title {
  display: flex;
  justify-content: start;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.4);
  color: white;
  font-weight: 400;
  font-size: 1.25rem;
  text-transform: uppercase;
  text-shadow: black 0.5px 1px 3px;
  writing-mode: sideways-lr;
  padding: 1rem;
  margin-bottom: 1rem;
  width: 10%;
  transition: all 0.5s ease;
}
.card-container:hover .card-title {
  background: rgba(110, 10, 10);
  margin-bottom: 0;
  font-weight: 600;
  width: 12%;
}
.card-info {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
  width: 90%;
  background: linear-gradient(75deg, rgb(255, 255, 255) 0%, rgb(226, 225, 225) 100%);
}
.card-container:hover .card-info {
  margin-bottom: 0;
  width: 88%;
}
.card-thumb {
  overflow: hidden;
}
.card-thumb-img {
  height: 19rem;
  transition: transform 2s ease;
}
.card-container:hover .card-thumb-img {
  height: 21rem;
  transform: scale(1.1);
}
.card-features {
  display: flex;
  padding: 0.5rem;
  gap: 1rem;
}
.feature-item {
  display: flex;
  align-items: center;
  gap: 0.25rem;
  font-size: 0.8rem;
}
.card-link {
  display: flex;
  justify-content: end;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem;
  text-decoration: none;
  text-transform: uppercase;
  font-size: 0.85rem;
  color:  rgba(110, 13, 13, 1);
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .card-features {
    gap: 2rem;
  }
  .feature-item {
    gap: 0.75rem;
  }
}

/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {

}
</style>