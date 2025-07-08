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
      <div class="card-services">
        <CardItem
          v-for="serv in listServices" :key="serv.title"
          :card-title="serv.title"
          :card-text="serv.text"
        />
      </div>
    </section>
    <section class="home-section-compliance">
      <SectionContainer :section-content="sectionsContent['compliance']" />
    </section>
    <section class="home-section-releases">
      <SectionContainer :section-content="sectionsContent['releases']" />
      <div class="releases-gallery">
        <CardGallery v-for="i in 2" :key="i"></CardGallery>
      </div>
    </section>
    <section class="home-section-contact">
      <SectionContainer :section-content="sectionsContent['contact']" />
      <ContactForm/>
    </section>
  </div>
</template>
<script>
import CardGallery from '@/components/CardGallery.vue';
import CardItem from '@/components/CardItem.vue';
import ContactForm from '@/components/ContactForm.vue';
import SectionContainer from '@/components/SectionContainer.vue';

/**
 * Página principal de apresentação do site.
 */
export default ({
  name: 'HomeView',
  components: {
    CardGallery,
    CardItem,
    ContactForm,
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
      'releases': {
        mainTitle: 'Lançamentos',
        subTitle: 'Empreendimentos em foco',
        paragraphs: [
          'Conheça os empreendimentos mais recentes desenvolvidos pela B2 Engenharia & Construção,'+
          ' que refletem nosso compromisso com a qualidade, inovação e eficiência.'+
          ' Para explorar o portfólio completo de obras e projetos, acesse a aba "Empreendimentos".'
        ]
      },
      'contact': {
        mainTitle: 'Fale Conosco',
        subTitle: 'Compartilhe seu sonho',
        paragraphs: []
      },
    },
    listServices: [
      {
        'title': 'Loteamento aberto e fechado',
        'text': 'Planejamento, aprovação e execução de loteamentos com foco em mobilidade, segurança e infraestrutura de qualidade.',
      },
      {
        'title': 'Desenvolvimento Imobiliário',
        'text': 'Gestão completa de empreendimentos, desde a viabilidade até a comercialização, com análise estratégica do mercado.',
      },
      {
        'title': 'Estruturação de Operações Financeiras',
        'text': 'Captação e estruturação de recursos financeiros para viabilização e alavancagem de projetos imobiliários e de infraestrutura.',
      },
      {
        'title': 'Edificações horizontais e verticais',
        'text': 'Construção de residenciais, comerciais e corporativos com soluções técnicas eficientes e alto padrão construtivo.',
      },
      {
        'title': 'Usinas Solares',
        'text': 'Implantação de usinas fotovoltaicas com foco em eficiência energética e retorno sustentável para investidores e parceiros.',
      },
      {
        'title': 'Retrofit de Edificações',
        'text': 'Requalificação de imóveis com foco na valorização patrimonial, eficiência operacional e adequação às normas atuais.',
      },
      {
        'title': 'Infraestrutura',
        'text': 'Execução de obras de infraestrutura urbana e industrial, com foco em durabilidade, funcionalidade e responsabilidade ambiental.',
      },
      {
        'title': 'Galpões Logísticos',
        'text': 'Projetos e construção de centros logísticos otimizados, com alto desempenho operacional e adaptabilidade às demandas do setor.',
      }
    ]
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
.home-section-services {
  background: radial-gradient(circle, rgb(80, 10, 10) 0%, rgba(0, 0, 0, 1) 100%);
  padding-bottom: 2rem;
  color: white;
}
.card-services {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin: 0rem 1rem;
}
.releases-gallery {
  display: flex;
  flex-direction: column;
  margin: 0rem 1rem;
  gap: 0.5rem;
}
.home-section-releases {
  padding-bottom: 1rem;
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