<template>
  <v-carousel v-model="currentSlide" cycle :interval="4000" :show-arrows="false" delimiter-icon="mdi-square"
    height="100vh">
    <v-carousel-item v-for="(image, i) in images" :key="i" :src="image.path" cover class="zoom-in" />
    <v-container class="caption-container">
      <h2 class="caption-text">{{ images[currentSlide].caption }}</h2>
    </v-container>
  </v-carousel>
  <div class="home-container">
    <section class="home-section-company">
      <SectionContainer :section-content="sectionsContent['company']" />
    </section>
    <section class="home-section-services">
      <SectionContainer :section-content="sectionsContent['services']" />
        <ul>
          <li v-for="x in 5" :key="x">
            test_{{ x }}
          </li>
        </ul>
    </section>
    <section class="home-section-compliance">
      <SectionContainer :section-content="sectionsContent['compliance']" />
    </section>
  </div>
</template>
<script>
import SectionContainer from '@/components/SectionContainer.vue';

/**
 * Página principal de apresentação do site.
 */
export default ({
  name: 'HomeView',
  components: {
    SectionContainer
  },
  data: () => ({
    images: [
      {
        path: require('@/assets/carousel/home-img-1.webp'),
        caption: 'Viabilizando os seus sonhos'
      },
      {
        path: require('@/assets/carousel/home-img-2.webp'),
        caption: 'Construindo com integridade e inovação'
      },
      {
        path: require('@/assets/carousel/home-img-3.webp'),
        caption: 'Alcançando novos horizontes'
      },
      {
        path: require('@/assets/carousel/home-img-4.webp'),
        caption: 'Pioneirismo em cada detalhe'
      }
    ],
    currentSlide: 0,
    sectionsContent: {
      'company': {
        mainTitle: 'A Empresa',
        subTitle: 'B2 Engenharia & Construção',
        paragraphs: [
          'A B2 Engenharia e Construção nasceu com o propósito de viabilizar empreendimentos por meio de uma compreensão'+
          'aprofundada do mercado e das variáveis determinantes para o sucesso de cada projeto.Com respeito aos sonhos'+
          'de nossos parceiros, atuamos de forma sustentável, apoiados na ampla experiência de nossos profissionais em'+
          'obras de grande porte.',

          'Nosso trabalho é fortemente voltado para a Incorporação Imobiliária, tanto em projetos comerciais quanto'+
          'residenciais. Atuamos desde a concepção e aprovação até a execução completa do empreendimento. Para'+
          'iniciativas que exigem aporte financeiro, realizamos toda a captação de recursos necessária para viabilizar sua implantação.',

          'Com profundo conhecimento do setor, a B2 desenvolve soluções inteligentes e personalizadas para diferentes'+
          'perfis de público e regiões. Seguimos rigorosamente nossa política de Compliance e mantemos uma gestão ativa'+
          'nos empreendimentos, com o objetivo de mitigar riscos e potencializar os resultados.'
        ]
      },
      'services': {
        mainTitle: 'Nossos Serviços',
        subTitle: 'Engenharia de qualidade',
        paragraphs: []
      },
      'compliance': {
        mainTitle: 'Compliance',
        subTitle: 'Ética e Conformidade',
        paragraphs: [
          'A política de Compliance da B2 Engenharia & Construção está fundamentada no rigoroso cumprimento das normas'+
          'e legislações vigentes. Esse compromisso abrange todas as áreas da empresa, incluindo segurança do trabalho,'+
          'operações, contabilidade, fiscal, questões trabalhistas e responsabilidade socioambiental.',

          'Como parte das ações preventivas e de monitoramento, a B2 disponibiliza seu Código de Ética e Conduta,'+
          'oferecendo um canal de comunicação direto e transparente. Esse canal é acessível a todos que se relacionam com'+
          'a empresa, seja de forma direta ou indireta — como colaboradores, subcontratados, parceiros, clientes e demais partes interessadas.'
        ]
      },
    }
  }),
});
</script>
<style scoped>
.zoom-in {
  animation: zoomIn 4.5s ease-in;
  transition: transform 0.1s ease-in;
}
.caption-container {
  position: absolute;
  top: 72%;
  left: 2%;
  width: 100%;
}
.caption-text {
  color: white;
  font-size: 2rem;
  font-weight: bold;
  text-transform: uppercase;
  text-align: left;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
}
.home-container {
  display: flex;
  flex-direction: column;
}
/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .caption-container {
    position: absolute;
    top: 50%;
    left: 5%;
    width: 24rem;
  }
  .caption-text {
    font-size: 2.5rem;
  }
}
/**
 * Dispositivos médios
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {
  .caption-container {
    position: absolute;
    top: 50%;
    left: 12%;
    width: 36rem;
  }
  .caption-text {
    font-size: 3.5rem;
  }
}

/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1264px) {
  .home-container {
    max-width: 1300px;
  }
}

/* Seção para Animações/Transições personalizadas*/
@keyframes zoomIn {
  0% {
    transform: scale(1) translateX(0) translateY(0);
  }
  100% {
    transform: scale(1.03) translateX(-1%) translateY(-1%);
  }
}
</style>