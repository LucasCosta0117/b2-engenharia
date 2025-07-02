<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="gallery-container">
    <span class="gallery-title">
      Galeria
    </span>
    <div class="card-gallery-container">
      <CardGallery v-for="i in 8" :key="i"></CardGallery>
    </div>
  </v-container>
</template>
<script>
import HeaderPage from '@/components/HeaderPage.vue';
import CardGallery from '@/components/CardGallery.vue';

export default {
  name: 'GalleryView',
  components: {
    HeaderPage,
    CardGallery
  },
  data: () => ({
    headerImage: require("@/assets/image/gallery-header.webp"),
    headerTitle: 'Nossos empreendimentos'
  }),
}
</script>
<style scoped>
.gallery-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.gallery-title {
  text-transform: uppercase;
  font-size: 1.25rem;
  border-bottom: solid goldenrod 1px;
  margin: 1rem 2rem;
  font-weight: 300;
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .card-gallery-container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 2rem;
  }
  .gallery-title {
    font-size: 1.5rem;
    margin: 1.5rem 2rem;
  }
}

/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .gallery-container {
    max-width: 1300px;
  }
  .card-gallery-container {
    gap: 3rem;
  }
  .gallery-title {
    margin: 3rem 2rem;
  }
}
</style>