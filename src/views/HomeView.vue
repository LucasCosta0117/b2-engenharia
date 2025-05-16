<template>
  <v-carousel
    cycle
    :interval="4000"
    :show-arrows="false"
    delimiter-icon="mdi-square"
    height="100vh"
  >
    <v-carousel-item
      v-for="(image, i) in images"
      :key="i"
      :src="image"
      cover
      class="zoom-in"
    >
    </v-carousel-item>
  </v-carousel>
  <div class="test">
    test
  </div>
</template>

<script>
export default ({
  name: 'HomeView',
  components: {},
  data: () => ({
    images: [
      require('@/assets/carousel/home-img-1.jpg'),
      require('@/assets/carousel/home-img-2.jpg'),
      require('@/assets/carousel/home-img-3.jpg'),
      require('@/assets/carousel/home-img-4.jpg')
    ]
  }),
});
</script>
<style scoped>
.zoom-in {
  animation: zoomIn 4.5s ease-in;
  transition: transform 0.1s ease-in;
}
.test {
  height: 800px;
}

@keyframes zoomIn {
  0% {
    transform: scale(1) translateX(0) translateY(0);
  }
  100% {
    transform: scale(1.03) translateX(-1%) translateY(-1%);
  }
}
</style>