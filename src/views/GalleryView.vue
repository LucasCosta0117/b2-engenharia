<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="gallery-container">
    <SiteUnderUpdate></SiteUnderUpdate>
  </v-container>
</template>
<script>
import SiteUnderUpdate from '@/components/SiteUnderUpdate.vue';
import HeaderPage from '@/components/HeaderPage.vue';

export default {
  name: 'GalleryView',
  components: {
    SiteUnderUpdate,
    HeaderPage
  },
  data: () => ({
    headerImage: require("@/assets/image/gallery-header.jpg"),
    headerTitle: 'Nossos empreendimentos'
  }),
}
</script>
<style scoped>
</style>