<template>
  <div>
    <v-img
      :src="headerImage"
      cover
      class="header-image"
    />
    <h2 class="header-title" >{{ headerTitle }}</h2>
  </div>
</template>
<script>

export default {
  name: 'ServicesView',
  props: {
    headerImage: {
      type: String,
      require: true,
      default:() => {
        return require("@/assets/image/partners-header.webp")
      }
    },
    headerTitle: {
      type: String,
      require: true,
      default: 'B2 Engenharia'
    }
  },
  data: () => ({
    //
  }),
}
</script>
<style scoped>
.header-image {
  height: 20rem;
  box-shadow: 0px 1px 5px rgb(60, 60, 60);
}
.header-title {
  position: absolute;
  top: 15%;
  left: 5%;
  text-align: left;
  text-transform: uppercase;
  color: white;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.6);
  max-width: 10rem;
}


/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .header-title {
    font-size: 2rem;
    top: 12%;
  }
}
/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .header-image {
    height: 30rem;
  }
  .header-title {
    font-size: 2.5rem;
    top: 20%;
    max-width: 15rem;
  }
}
</style>