<template>
  <HeaderPage :header-image="headerImage" :header-title="headerTitle" />
  <v-container class="services-container">
    <div class="section-services-p1">
      <SectionTitle :main-title="'O Que Fazemos'" :sub-title="'Da concepção à entrega'" />
      <div class="section-paragraph">
        <p>
          Com ampla experiência no setor da construção civil, nossa empresa oferece soluções completas que vão desde o
          desenvolvimento imobiliário e estruturação financeira até a execução de obras de infraestrutura e edificações
          de alto padrão. Atuamos de forma estratégica e integrada, aliando inovação técnica, eficiência operacional e
          compromisso com a qualidade. Nosso portfólio abrange loteamentos, retrofit, usinas solares, galpões logísticos
          e projetos urbanos, sempre com foco em resultado, sustentabilidade e valorização dos ativos.
        </p>
      </div>
    </div>
    <div class="section-services-p2">
      <SectionTitle :main-title="'Áreas de Atuação'" :sub-title="''" />
      <CardServices v-for="serv of listServices" :key="serv.title"
        class="card-service-item"
        :title="serv.title" 
        :paragraph="serv.paragraph"
        :imageName="serv.imageName"
      />
    </div>
  </v-container>
</template>
<script>
import CardServices from '@/components/CardServices.vue';
import HeaderPage from '@/components/HeaderPage.vue';
import SectionTitle from '@/components/SectionTitle.vue';

export default {
  name: 'ServicesView',
  components: {
    CardServices,
    HeaderPage,
    SectionTitle
  },
  data: () => ({
    headerImage: require("@/assets/image/services-header.webp"),
    headerTitle: 'Nossos serviços',
    listServices: [
      {
        title: 'Loteamento aberto e fechado',
        paragraph: 'A empresa atua na concepção e execução de loteamentos residenciais e comerciais, abertos ou fechados, priorizando soluções de mobilidade urbana, segurança e infraestrutura de alto padrão. O serviço contempla desde o planejamento urbanístico e trâmites de aprovação junto aos órgãos competentes até a completa implantação das obras, garantindo funcionalidade e valorização do empreendimento.',
        imageName: 'lote.webp'
      },
      {
        title: 'Desenvolvimento Imobiliário',
        paragraph: 'Oferecemos gestão integral do ciclo de empreendimentos imobiliários, iniciando na análise de viabilidade técnica e econômica, passando pela concepção do projeto e licenciamento, até as etapas finais de incorporação e comercialização. Atuamos de forma estratégica, alinhando interesses de investidores, construtores e o mercado consumidor para garantir solidez e retorno ao negócio.',
        imageName: 'des_imob.webp'
      },
      {
        title: 'Estruturação de Operações Financeiras',
        paragraph: 'Realizamos a captação e estruturação de recursos financeiros voltados à viabilização de projetos imobiliários e de infraestrutura. Apoiamos nossos parceiros na modelagem de operações com segurança jurídica, análise de risco e atratividade econômica, conectando oportunidades do setor com agentes financeiros e investidores institucionais.',
        imageName: 'oper_fin.webp'
      },
      {
        title: 'Edificações horizontais e verticais',
        paragraph: 'Executamos obras residenciais, comerciais e corporativas com excelência técnica e foco em qualidade construtiva. Utilizamos métodos modernos de engenharia e gestão para garantir o cumprimento de prazos, controle de custos e desempenho funcional, tanto em edificações térreas quanto em empreendimentos verticais de média e alta complexidade.',
        imageName: 'edif_horiz.webp'
      },
      {
        title: 'Usinas Solares',
        paragraph: 'Atuamos na implantação de usinas fotovoltaicas, desde a fase de projeto até a entrega operacional, promovendo soluções sustentáveis e eficientes em geração de energia. Com domínio técnico e visão estratégica, desenvolvemos ativos que geram retorno financeiro, estabilidade energética e benefícios ambientais para investidores e comunidades.',
        imageName: 'solar_power.webp'
      },
      {
        title: 'Retrofit de Edificações',
        paragraph: 'Especialistas em modernização de imóveis, realizamos projetos de retrofit que promovem a revitalização estética, funcional e normativa de edifícios. O serviço visa valorizar o patrimônio, aumentar a eficiência operacional e garantir conformidade com as exigências legais, com mínima interferência na rotina dos usuários e uso racional dos recursos.',
        imageName: 'retrofit.webp'
      },
      {
        title: 'Infraestrutura',
        paragraph: 'Executamos obras de infraestrutura urbana e industrial com foco em desempenho técnico, durabilidade e sustentabilidade. Atuamos em projetos como vias de grande fluxo, redes de drenagem, saneamento, terraplanagem e obras de arte especiais, garantindo soluções seguras e adaptadas às necessidades da região e do empreendimento.',
        imageName: 'infra.webp'
      },
      {
        title: 'Galpões Logísticos',
        paragraph: 'Desenvolvemos projetos e executamos construções de galpões logísticos e centros de distribuição otimizados para alta eficiência operacional. Nossos projetos aliam funcionalidade, flexibilidade e desempenho, atendendo às demandas de armazenagem, circulação e segurança requeridas pelos setores industrial, varejista e de e-commerce.',
        imageName: 'galpao.webp'
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
  padding: 2rem 1rem;
}
.section-services-p1 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
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
.section-services-p2 {
  display: flex;
  flex-direction: column;
  gap: 1rem;
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
    gap: 3rem;
    margin-bottom: 3rem;
  }
  .section-paragraph {
    font-size: 1.1rem;
  }
  .card-service-item:nth-child(odd) {
    flex-direction: row-reverse;
  }
  .section-services-p2 {
    gap: 1.5rem;
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