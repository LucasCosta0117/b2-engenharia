<template>
  <v-container class="contact-container">
    <SiteUnderUpdate></SiteUnderUpdate>
  </v-container>
</template>
<script>
import SiteUnderUpdate from '@/components/SiteUnderUpdate.vue';

export default {
  name: 'ContactView',
  components: {
    SiteUnderUpdate,
  },
  data: () => ({
    headerImage: require("@/assets/image/about-header.webp"),
    headerTitle: 'Sobre a empresa'
  }),
}
</script>
<style scoped>
</style>