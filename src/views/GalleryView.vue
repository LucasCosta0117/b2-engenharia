<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="gallery-container">
    <SectionTitle :title="'Galeria'"></SectionTitle>
    <div class="card-gallery-container">
      <CardGallery v-for="i in 8" :key="i"></CardGallery>
    </div>
  </v-container>
</template>
<script>
import HeaderPage from '@/components/HeaderPage.vue';
import CardGallery from '@/components/CardGallery.vue';
import SectionTitle from '@/components/SectionTitle.vue';

export default {
  name: 'GalleryView',
  components: {
    HeaderPage,
    CardGallery,
    SectionTitle
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
}
</style>