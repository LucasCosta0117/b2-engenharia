<template>
  <div class="card-container">
    <div class="card-title">
      {{ title }}
    </div>
    <div class="card-info">
      <div class="card-thumb">
        <v-img cover class="card-thumb-img" :src="thumbUrl"/>
      </div>
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
    </div>
  </div>
</template>
<script>
/**
 * Card que expoem um item do portifólio.
 */
export default {
  name: 'CardGallery',
  data() {
    return {
      title: 'Mamanuca Praia do Forte',
      thumbUrl: require('@/assets/image/gallery-header.webp'),
      feature: {
        bedrooms: '4 quartos',
        area: '45m²',
        city: 'Praia do Forte - BA',
        launch: 'jun/2025'
      }
    }
  }
}
</script>
<style scoped>
.card-container {
  display: flex;
  height: 25rem;
}
.card-title {
  display: flex;
  justify-content: start;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.8);
  color: white;
  font-weight: 400;
  font-size: 1.25rem;
  text-transform: uppercase;
  writing-mode: sideways-lr;
  padding: 2rem;
  margin-bottom: 1rem;
  width: 30%;
  transition: all 0.5s ease;
}
.card-container:hover .card-title {
  background: linear-gradient(45deg, rgba(0, 0, 0, 1) 0%, rgba(110, 13, 13, 1) 100%);
  margin-bottom: 0;
  font-weight: 600;
  width: 20%;
}
.card-info {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
  width: 70%;
  background: linear-gradient(75deg, rgb(255, 255, 255) 0%, rgb(221, 217, 217) 100%);
}
.card-container:hover .card-info {
  margin-bottom: 0;
  width: 80%;
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

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .card-container {
    width: 48%;
  }
}

/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .card-container {
    width: 32%;
  }
}
</style>