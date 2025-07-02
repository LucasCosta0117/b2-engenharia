<template>
  <div class="session-title">
    {{ title }}
  </div>
</template>
<script>
/**
 * Componente responsável por padronizar os títulos das sessões na aplicação.
 */
export default {
  name: 'SessionTitle',
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
.session-title {
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
  .session-title {
    font-size: 1.5rem;
    margin: 1.5rem 2rem;
  }
}
/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .session-title {
    margin: 3rem 2rem;
  }
}
</style>