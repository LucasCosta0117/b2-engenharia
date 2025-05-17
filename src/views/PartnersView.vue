<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="partners-container">
    <SiteUnderUpdate></SiteUnderUpdate>
  </v-container>
</template>
<script>
import SiteUnderUpdate from '@/components/SiteUnderUpdate.vue';
import HeaderPage from '@/components/HeaderPage.vue';

export default {
  name: 'PartnersView',
  components: {
    SiteUnderUpdate,
    HeaderPage
  },
  data: () => ({
    headerImage: require("@/assets/image/partners-header.webp"),
    headerTitle: 'Parceiros comerciais'
  }),
}
</script>
<style scoped>
</style>