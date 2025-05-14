<template>
  <HelloWorld />
</template>

<script>
import { defineComponent } from 'vue';

// Components
import HelloWorld from '../components/HelloWorld.vue';

export default defineComponent({
  name: 'HomeView',

  components: {
    HelloWorld,
  },
});
</script>
<style scoped>

/* Pequenos dispositivos (celulares maiores e tablets, entre 481px e 767px) */
@media (min-width: 481px) {

}
/* Dispositivos médios (tablets em retrato, entre 768px e 1023px) */
@media (min-width: 768px) {

}
/* Dispositivos grandes (tablets em paisagem / laptops pequenos) */
@media (min-width: 1024px) {

}
/* Telas grandes (desktops, TVs etc.) */
@media (min-width: 1280px) {

}
</style>
