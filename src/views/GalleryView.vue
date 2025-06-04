<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="gallery-container">
     <CardGallery v-for="i in 2" :key="i"></CardGallery>
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
</style>