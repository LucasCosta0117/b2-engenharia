<template>
  <v-app>
    <NavBar></NavBar>
    <v-main>
      <router-view/>
    </v-main>
    <FooterPage></FooterPage>
  </v-app>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import FooterPage from '@/components/FooterPage.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    FooterPage
  },
  data: () => ({
    //
  }),
}
</script>
