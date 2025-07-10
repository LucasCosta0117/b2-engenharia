<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="about-container">
    <div class="section-about-p1">
      <SectionTitle class="section-title" :main-title="sectionTitle.mainTitle"
        :sub-title="sectionTitle.subTitle" />
      <div class="section-paragraph">
        <p>
          Na B2 Engenharia e Construção, oferecemos soluções completas para o setor imobiliário e de infraestrutura.
          Atuamos desde a concepção até a execução dos empreendimentos, sempre comprometidos com a qualidade, eficiência
          e sustentabilidade. Nosso time multidisciplinar alia experiência técnica à gestão estratégica, garantindo
          entregas sólidas, inovadoras e com alto padrão de excelência.
        </p>
      </div>
    </div>
  </v-container>
</template>
<script>
import HeaderPage from '@/components/HeaderPage.vue';
import SectionTitle from '@/components/SectionTitle.vue';

export default {
  name: 'AboutView',
  components: {
    HeaderPage,
    SectionTitle
  },
  data: () => ({
    headerImage: require("@/assets/image/about-header.webp"),
    headerTitle: 'Sobre a empresa',
    sectionTitle: {
      mainTitle: 'Quem Somos',
      subTitle: 'Transformamos projetos em realidade'
    },
  }),
}
</script>
<style scoped>
.section-about-p1 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.section-title {
  margin: 0 1rem;
}
.section-paragraph {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  font-size: 1rem;
  text-align: justify;
  text-indent: 1rem;
  margin: 0rem 1rem;
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
  .about-container {
    max-width: 1000px;
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
  .about-container {
    max-width: 1200px;
  }
}
</style>