<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="about-container">
    <SiteUnderUpdate></SiteUnderUpdate>
  </v-container>
</template>
<script>
import SiteUnderUpdate from '@/components/SiteUnderUpdate.vue';
import HeaderPage from '@/components/HeaderPage.vue';

export default {
  name: 'AboutView',
  components: {
    SiteUnderUpdate,
    HeaderPage
  },
  data: () => ({
    headerImage: require("@/assets/image/about-header.webp"),
    headerTitle: 'Sobre a empresa'
  }),
}
</script>
<style scoped>
</style>