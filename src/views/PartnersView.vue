<template>
  <HeaderPage :header-image="headerImage" :header-title="headerTitle" />
  <v-container class="partners-container">
    <div class="section-partners-p1">
      <SectionTitle class="section-title" :main-title="'Nossos Parceiros'" :sub-title="'Confiança mútua'" />
      <div class="section-paragraph">
        <p>
          A B2 Engenharia & Construção valoriza alianças estratégicas que fortalecem sua atuação no mercado. Nossos
          parceiros são fundamentais na entrega de soluções inovadoras, sustentáveis e de alto desempenho, contribuindo
          diretamente para o sucesso dos empreendimentos que desenvolvemos. Acreditamos que relações pautadas pela
          confiança, transparência e comprometimento geram resultados sólidos e duradouros.
        </p>
      </div>
      <div class="section-imgs-p1">
        <div class="section-img" v-for="img in sectionImgs" :key="img.alt" 
          :style="{ backgroundImage: `url(${img.path})` }" 
          :title="img.alt"
          :alt="img.alt"
        >
        </div>
      </div>
    </div>
  </v-container>
</template>
<script>
import HeaderPage from '@/components/HeaderPage.vue';
import SectionTitle from '@/components/SectionTitle.vue';

export default {
  name: 'PartnersView',
  components: {
    HeaderPage,
    SectionTitle
  },
  data: () => ({
    headerImage: require("@/assets/image/partners-header.webp"),
    headerTitle: 'Parceiros comerciais',
    sectionImgs: [
      {
        path: require('@/assets/image/partner-mh2.png'),
        alt: 'MH2 Soluções em Engenharia',
      },
      {
        path: require('@/assets/image/partner-vernace.png'),
        alt: 'Vernace Capital Partners',
      },
      {
        path: require('@/assets/image/partner-banneg.png'),
        alt: 'Banneg Banco de Negócios',
      },
      {
        path: require('@/assets/image/partner-camara.png'),
        alt: 'Camara IA',
      },
      {
        path: require('@/assets/image/partner-embasa.png'),
        alt: 'Embasa',
      }
    ]
  }),
}
</script>
<style scoped>
.partners-container {
  display: flex;
  flex-direction: column;
  padding: 2rem 1rem;
}
.section-partners-p1 {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}
.section-paragraph {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  font-size: 1rem;
  text-align: justify;
  text-indent: 1rem;
}
.section-imgs-p1 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.section-img {
  width: 100%;
  height: 5rem;
  background-size: contain;
  background-position: center;
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .section-imgs-p1 {
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
    gap: 2rem;
  }
  .section-img {
    width: 40%;
    transition: transform 1s ease;
  }
  .section-img:hover {
    transform: scale(1.1);
  }
}
/**
 * Dispositivos médios
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .partners-container {
    max-width: 1000px;
  }
  .section-paragraph {
    font-size: 1.1rem;
  }
  .section-img {
    width: 30%;
  }
  .section-partners-p1 { 
    margin-bottom: 2rem;
  }
}

/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1400px) {
  .partners-container {
    max-width: 1200px;
  }
}
</style>