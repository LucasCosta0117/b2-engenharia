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
  background-color: rgb(85, 4, 4);
  color: white;
  font-weight: 600;
  font-size: 1.1rem;
  text-transform: uppercase;
  writing-mode: sideways-lr;
  padding: 1.5rem;
  margin-bottom: 1rem;
  width: 30%;
}
.card-info {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
  width: 70%;
  background: linear-gradient(75deg, rgb(255, 255, 255) 0%, rgb(221, 217, 217) 100%);
}
.card-thumb {

}
.card-thumb-img {
  height: 19rem;
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
</style>