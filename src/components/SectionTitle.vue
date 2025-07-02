<template>
  <div class="section-title">
    {{ title }}
  </div>
</template>
<script>
/**
 * Componente responsável por padronizar os títulos das sessões na aplicação.
 */
export default {
  name: 'SectionTitle',
  props: {
    /**
     * Define a string utilizada como Título.
     */
    title: {
      type: String,
    }
  },
  data() {
    return {}
  }
}
</script>
<style scoped>
.section-title {
  color: black;
  text-transform: uppercase;
  font-size: 1.25rem;
  border-bottom: solid goldenrod 1px;
  margin: 1rem 2rem;
  font-weight: 300;
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .section-title {
    font-size: 1.5rem;
    margin: 1.5rem 2rem;
  }
}
/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .section-title {
    margin: 3rem 2rem;
  }
}
</style>