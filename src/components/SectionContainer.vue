<template>
  <div class="section-container">
    <SectionTitle
      class="section-main-title"
      :main-title="sectionContent.mainTitle"
      :sub-title="sectionContent.subTitle"
    />
    <div v-if="sectionContent.paragraphs.length > 0" class="section-paragraph">
      <p v-for="paragraph in sectionContent.paragraphs" :key="paragraph">
        {{ paragraph }}
      </p>
    </div>
  </div>
</template>
<script>
import SectionTitle from './SectionTitle.vue';
/**
 * Componente responsável por padronizar as seções de conteúdo dentro do site,
 * organizando titulo, subtitulo e parágráfos.
 */
export default {
  name: 'SectionContainer',
  components: {
    SectionTitle,
  },
  props: {
    /**
     * Contem os elementos responsáveis pelo conteúdo da seção.
     */
    sectionContent: {
      type: Object,
      required: true
    }
  },
  data() {
    return {

    }
  }
}
</script>
<style scoped>
.section-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin: 0rem 1rem;
}
.section-paragraph {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  font-size: 1rem;
  text-align: justify;
  text-indent: 1rem;
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
  .section-container {
    flex-direction: row;
  }
  .section-main-title {
    min-width: 40%;
  }
  .section-paragraph {
    font-size: 1.1rem;
  }
}
/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1400px) {
  .section-paragraph {
    font-size: 1.2rem;
  }
}
</style>