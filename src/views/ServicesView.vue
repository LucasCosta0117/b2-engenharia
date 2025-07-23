<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <div class="services-container">
    <CardServices
      v-for="serv of listServices" :key="serv.title"
      :title="serv.title"
      :paragraph="serv.paragraph"
      :imageName="serv.imageName"
    />
  </div>
</template>
<script>
import CardServices from '@/components/CardServices.vue';
import HeaderPage from '@/components/HeaderPage.vue';

export default {
  name: 'ServicesView',
  components: {
    CardServices,
    HeaderPage
  },
  data: () => ({
    headerImage: require("@/assets/image/services-header.webp"),
    headerTitle: 'Nossos serviços',
    listServices: [
      {
        title: 'Loteamento aberto e fechado',
        paragraph: 'Planejamento, aprovação e execução de loteamentos com foco em mobilidade, segurança e infraestrutura de qualidade.',
        imageName: 'compliance.webp'
      },
      {
        title: 'Desenvolvimento Imobiliário',
        paragraph: 'Gestão completa de empreendimentos, desde a viabilidade até a comercialização, com análise estratégica do mercado.',
        imageName: 'compliance.webp'
      },
      {
        title: 'Estruturação de Operações Financeiras',
        paragraph: 'Captação e estruturação de recursos financeiros para viabilização e alavancagem de projetos imobiliários e de infraestrutura.',
        imageName: 'compliance.webp'
      },
      {
        title: 'Edificações horizontais e verticais',
        paragraph: 'Construção de residenciais, comerciais e corporativos com soluções técnicas eficientes e alto padrão construtivo.',
        imageName: 'compliance.webp'
      },
      {
        title: 'Usinas Solares',
        paragraph: 'Implantação de usinas fotovoltaicas com foco em eficiência energética e retorno sustentável para investidores e parceiros.',
        imageName: 'compliance.webp'
      },
      {
        title: 'Retrofit de Edificações',
        text: 'Requalificação de imóveis com foco na valorização patrimonial, eficiência operacional e adequação às normas atuais.',
        imageName: 'compliance.webp'
      },
      {
        title: 'Infraestrutura',
        paragraph: 'Execução de obras de infraestrutura urbana e industrial, com foco em durabilidade, funcionalidade e responsabilidade ambiental.',
        imageName: 'compliance.webp'
      },
      {
        title: 'Galpões Logísticos',
        paragraph: 'Projetos e construção de centros logísticos otimizados, com alto desempenho operacional e adaptabilidade às demandas do setor.',
        imageName: 'compliance.webp'
      }
    ]
  }),
}
</script>
<style scoped>
.services-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin: 4rem 1rem;
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
  .services-container {
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
  .services-container {
    max-width: 1200px;
  }
}
</style>