<template>
  <v-carousel v-model="currentSlide" cycle :interval="4000" :show-arrows="false" delimiter-icon="mdi-square"
    height="100vh">
    <v-carousel-item v-for="(image, i) in images" :key="i" :src="image.path" cover class="zoom-in" />
    <v-container class="caption-container">
      <h2 class="caption-text">{{ images[currentSlide].caption }}</h2>
    </v-container>
  </v-carousel>
  <div class="home-container">
    <section class="home-section home-section-company">
      <div class="section-company-title">
        <SectionTitle class="section-title" :main-title="sectionsTitles['company'].mainTitle"
          :sub-title="sectionsTitles['company'].subTitle" />
        <div class="section-company-img"></div>
      </div>
      <div class="section-paragraph">
        <p>
          A B2 Engenharia e Construção nasceu com o propósito de viabilizar empreendimentos por meio de uma compreensão
          aprofundada do mercado e das variáveis determinantes para o sucesso de cada projeto. Com respeito aos sonhos
          de nossos parceiros, atuamos de forma sustentável, apoiados na ampla experiência de nossos profissionais em
          obras de grande porte.
        </p>
        <p>
          Nosso trabalho é fortemente voltado para a Incorporação Imobiliária, tanto em projetos comerciais quanto
          residenciais. Atuamos desde a concepção e aprovação até a execução completa do empreendimento. Para
          iniciativas que exigem aporte financeiro, realizamos toda a captação de recursos necessária para viabilizar
          sua implantação.
        </p>
        <p>
          Com profundo conhecimento do setor, a B2 desenvolve soluções inteligentes e personalizadas para diferentes
          perfis de público e regiões. Seguimos rigorosamente nossa política de Compliance e mantemos uma gestão ativa
          nos empreendimentos, com o objetivo de mitigar riscos e potencializar os resultados.
        </p>
      </div>
    </section>
    <div class="bg-rg-red">
      <section class="home-section home-section-services">
        <SectionTitle class="section-title" :main-title="sectionsTitles['services'].mainTitle"
          :sub-title="sectionsTitles['services'].subTitle" />
        <div class="cards-services">
          <CardItem v-for="serv in listServices" :key="serv.title" :card-title="serv.title" :card-text="serv.text" />
        </div>
      </section>
    </div>
    <div class="bg-img-building">
      <section class="home-section home-section-compliance">
        <div class="section-compliance-p1">
          <SectionTitle class="section-title" :main-title="sectionsTitles['compliance'].mainTitle"
            :sub-title="sectionsTitles['compliance'].subTitle" />
          <div class="section-paragraph">
            <p>
              A política de Compliance da empresa está fundamentada no rigoroso cumprimento das normas
              e legislações vigentes. Como parte das ações preventivas e de monitoramento, a B2 disponibiliza
              seu Código de Ética e Conduta, oferecendo um canal de comunicação direto e transparente.
              Esse canal é acessível a todos que se relacionam conosco, seja de forma direta ou indireta —
              como colaboradores, subcontratados, parceiros, clientes e demais partes interessadas.
            </p>
          </div>
        </div>
        <div class="section-compliance-img"></div>
        <div class="section-compliance-p2">
          <div class="highlighted-paragraph">
            Nosso compromisso com a Ética e a Conformidade abrange todas as áreas da empresa.
          </div>
          <div>
            <ul class="section-compliance-list">
              <li>Segurança do Trabalho</li>
              <li>Operações</li>
              <li>Contabilidade</li>
              <li>Fiscal</li>
              <li>Questões Trabalhistas</li>
              <li>Responsabilidade Socioambiental</li>
            </ul>
          </div>
        </div>
      </section>
      <section class="home-section home-section-releases">
        <SectionTitle class="section-title" :main-title="sectionsTitles['releases'].mainTitle"
          :sub-title="sectionsTitles['releases'].subTitle" />
        <div class="cards-releases">
          <CardGallery v-for="i in 2" :key="i"></CardGallery>
        </div>
      </section>
    </div>
  </div>
  <section class="home-section home-section-contact">
    <SectionTitle class="section-title" :main-title="sectionsTitles['contact'].mainTitle"
      :sub-title="sectionsTitles['contact'].subTitle" />
    <ContactForm />
  </section>
</template>
<script>
import CardGallery from '@/components/CardGallery.vue';
import CardItem from '@/components/CardItem.vue';
import ContactForm from '@/components/ContactForm.vue';
import SectionTitle from '@/components/SectionTitle.vue';

/**
 * Página principal de apresentação do site.
 */
export default ({
  name: 'HomeView',
  components: {
    CardGallery,
    CardItem,
    ContactForm,
    SectionTitle
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
    sectionsTitles: {
      'company': {
        mainTitle: 'A Empresa',
        subTitle: 'B2 Engenharia & Construção'
      },
      'services': {
        mainTitle: 'Nossos Serviços',
        subTitle: 'Engenharia de qualidade'
      },
      'compliance': {
        mainTitle: 'Compliance',
        subTitle: 'Ética e Conformidade'
      },
      'releases': {
        mainTitle: 'Lançamentos',
        subTitle: 'Empreendimentos em foco'
      },
      'contact': {
        mainTitle: 'Fale Conosco',
        subTitle: 'Compartilhe seu sonho'
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
.home-section {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  padding: 2rem 0rem;
  margin: 0 auto;
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
.section-company-title {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.section-company-img {
  background-image: url('@/assets/image/vgp.webp');
  background-repeat: no-repeat;
  background-position: bottom;
  background-size: cover;
  max-width: 100%;
  height: 22rem;
  margin: 0rem 1rem;
  border-radius: 0.5rem;
}
.bg-rg-red {
  background: radial-gradient(circle, rgb(80, 10, 10) 0%, rgba(0, 0, 0, 1) 100%);
}
.bg-img-building {
  background-image: url('@/assets/image/building.webp');
  background-size: contain;
}
.home-section-services {
  color: white;
}
.cards-services {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin: 0rem 1rem;
}
.section-compliance-p1 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.section-compliance-img {
  background-image: url("@/assets/image/compliance.webp");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  max-width: 100%;
  height: 10rem;
  margin: 0rem 1rem;
  border-radius: 0.5rem;
}
.section-compliance-p2 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin: 0rem 1rem;
}
.highlighted-paragraph {
  font-size: 1.25rem;
  text-align: start;
  font-weight: 500;
}
.section-compliance-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.section-compliance-list li {
  border-left: 3px solid rgb(113, 10, 10);
  font-size: 1.15rem;
  padding-left: 0.5rem;
}
.cards-releases {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin: 0rem 1rem;
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
  .section-company-img {
    height: 20rem;
  }
  .cards-services {
    flex-direction: row;
    flex-wrap: wrap;
  }
  .section-compliance-img {
    height: 15rem;
    background-position: top;
  }
  .cards-releases {
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
  }
  .home-section-services {
    padding-bottom: 5rem;
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
  .home-container {
    align-items: center;
  }
  .section-paragraph {
    font-size: 1.1rem;
  }
  .bg-rg-red {
    width: 100%;
  }
  .home-section {
    max-width: 1000px;
  }
  .home-section-company {
    flex-direction: row;
  }
  .section-company-title {
    min-width: 40%;
  }
  .section-company-img {
    height: 22rem;
  }
  .home-section-compliance {
    gap: 2rem;
  }
  .section-compliance-img {
    height: 20rem;
  }
  .section-compliance-p2 {
    flex-direction: row;
    justify-content: space-evenly;
  }
  .section-compliance-p2 .highlighted-paragraph {
    width: 40%;
    font-size: 1.7rem;
  }
  .cards-releases .card-container{
    width: 48%;
  }
}

/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1400px) {
  .home-section {
    max-width: 1200px;
  }
  .section-company-img {
    height: 17rem;
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