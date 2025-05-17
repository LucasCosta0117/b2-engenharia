<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="services-container">
    <SiteUnderUpdate></SiteUnderUpdate>
  </v-container>
</template>
<script>
import SiteUnderUpdate from '@/components/SiteUnderUpdate.vue';
import HeaderPage from '@/components/HeaderPage.vue';

export default {
  name: 'ServicesView',
  components: {
    SiteUnderUpdate,
    HeaderPage
  },
  data: () => ({
    headerImage: require("@/assets/image/services-header.webp"),
    headerTitle: 'Nossos serviços'
  }),
}
</script>
<style scoped>
</style>