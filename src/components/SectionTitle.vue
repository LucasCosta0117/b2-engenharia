<template>
  <div class="section-title-container">
    <div>
      <span class="section-maintitle">
        {{ mainTitle }}
      </span>
    </div>
    <div>
      <span class="section-subtitle">
        {{ subTitle }}
      </span>
    </div>
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
    mainTitle: {
      type: String,
    },
    /**
     * Define a string utilizada como Título Secundário.
     */
    subTitle: {
      type: String,
    }
  },
  data() {
    return {}
  }
}
</script>
<style scoped>
.section-title-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.section-maintitle {
  text-transform: uppercase;
  font-size: 1.25rem;
  margin: 1rem 1rem;
  font-weight: 300;
  border-bottom: solid goldenrod 1px;
  padding-bottom: 0.5rem;
}
.section-subtitle {
  font-size: 1.25rem;
  margin: 0rem 1rem;
  font-weight: 600;
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {

}
/**
 * Dispositivos médios
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .section-maintitle {
    font-size: 1.75rem;
  }
  .section-subtitle {
    font-size: 1.5rem;
  }
}
/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1400px) {
}
</style>