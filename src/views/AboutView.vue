<template>
  <HeaderPage :header-image="headerImage" :header-title="headerTitle" />
  <v-container class="about-container">
    <div class="section-about-p1">
      <SectionTitle :main-title="sectionTitle.mainTitle" :sub-title="sectionTitle.subTitle" />
      <div class="section-paragraph">
        <p>
          Na B2 Engenharia e Construção, oferecemos soluções completas para o setor imobiliário e de infraestrutura.
          Atuamos desde a concepção até a execução dos empreendimentos, sempre comprometidos com a qualidade, eficiência
          e sustentabilidade. Nosso time multidisciplinar alia experiência técnica à gestão estratégica, garantindo
          entregas sólidas, inovadoras e com alto padrão de excelência.
        </p>
      </div>
      <div>
        <v-row class="ml-0 mr-0">
          <v-col cols="3" class="pa-1">
            <div class="section-imgs-p1 img-01-p1"></div>
          </v-col>
          <v-col cols="9" class="pa-1">
            <div class="section-imgs-p1 img-02-p1"></div>
          </v-col>
        </v-row>
        <v-row class="ml-0 mr-0">
          <v-col cols="5" class="pa-1">
            <div class="section-imgs-p1 img-03-p1"></div>
          </v-col>
          <v-col cols="7" class="pa-1">
            <div class="section-imgs-p1 img-04-p1"></div>
          </v-col>
        </v-row>
      </div>
    </div>
    <div class="section-about-p2">
      <SectionTitle :main-title="'Nossos Valores'" :sub-title="''" />
      <div class="cards-business-values">
        <CardIcon v-for="val in listBusinessValues" :key="val.title"
          class="card-business-item"
          :card-title="val.title" 
          :card-text="val.text"
          :card-icon="val.icon"
        />
      </div>
    </div>
    <div class="section-about-p3">
      <div class="section-p3-mission">
        <SectionTitle :main-title="'Missão'" :sub-title="''" />
        <div class="section-paragraph">
          <p>
            Promover o desenvolvimento imobiliário sustentável através de seus projetos e obras, influenciando e sendo
            influenciado pelas boas práticas que aparecem a cada dia no mercado.
          </p>
        </div>
      </div>
      <div class="section-p3-vision">
        <SectionTitle :main-title="'Visão'" :sub-title="''" />
        <div class="section-paragraph">
          <p>
            Ser reconhecida como uma das principais construtoras e incorporadoras em atuação no mercado.
          </p>
        </div>
      </div>
    </div>
    <div class="section-about-p4">
      <SectionTitle :main-title="'Sócios Fundadores'" :sub-title="''" />
      <div class="partners-paragraph">
        <div class="section-paragraph">
          <h3>
            <i class="mdi mdi-account-hard-hat worker-icon"></i>
            Vitor Brasileiro
          </h3>
          <p>
            Engenheiro Civil graduado pela Universidade Federal da Bahia, possui sólida experiência no setor
            da construção civil, com atuação em mais de 50 obras distribuídas em 8 estados brasileiros. Entre 2009 e
            2020,
            participou da incorporação e construção de aproximadamente 500.000m² em empreendimentos de grande porte,
            abrangendo segmentos como edificações verticais, condomínios horizontais, infraestrutura urbana, hospitais,
            aeroportos, arenas multiuso, usinas solares e obras industriais. Ao longo da carreira, esteve envolvido em
            projetos que somam mais de R$10 bilhões em volume de negócios, consolidando amplo know-how técnico e
            gerencial.
          </p>
        </div>
        <div class="section-paragraph">
          <h3>
            <i class="mdi mdi-account-hard-hat worker-icon"></i>
            Raul Barretto
          </h3>
          <p>
            Engenheiro Civil graduado pela Universidade Federal da Bahia, construiu sua trajetória profissional
            atuando em grandes obras e processos licitatórios em 6 estados brasileiros. Participou de projetos
            relevantes
            em áreas como rodovias, ferrovias, pontes, edificações públicas e incorporação imobiliária. Com passagens
            por
            empresas de referência nacional, acumulou expertise na gestão de contratos de alta complexidade e execução
            de
            empreendimentos de grande escala.
          </p>
        </div>
      </div>
    </div>
    <div class="section-about-p5">
      <SectionTitle :main-title="'Identidade Empresarial'" :sub-title="'Nossa Essência'" />
      <div class="section-paragraph">
        <p>
          A B2 Engenharia & Construção é uma empresa que une experiência técnica, visão estratégica de mercado e
          compromisso com a sustentabilidade para desenvolver e executar empreendimentos inteligentes em diversas
          regiões do país. Atuando nos segmentos de incorporação imobiliária, infraestrutura, energia solar, retrofit e
          edificações, a B2 alia sua capacidade de estruturação financeira com um modelo de gestão ativo, pautado por
          valores como integridade, responsabilidade e melhoria contínua. Com forte presença no setor de loteamentos e
          uma política rigorosa de compliance, a empresa se posiciona como parceira sólida para investidores e clientes
          que buscam excelência, segurança e resultados sustentáveis no mercado da construção civil.
        </p>
      </div>
    </div>
  </v-container>
</template>
<script>
import CardIcon from '@/components/CardIcon.vue';
import HeaderPage from '@/components/HeaderPage.vue';
import SectionTitle from '@/components/SectionTitle.vue';

export default {
  name: 'AboutView',
  components: {
    CardIcon,
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
    listBusinessValues: [
      {
        title: 'Dedicação Plena',
        text: 'Entendemos a dedicação como uma demonstração de humildade, disponibilidade e pró-atividade nas relações de trabalho. Através dela, assumimos a condição de agentes na conclusão dos objetivos que nos propomos a alcançar.',
        icon: 'mdi-hand-heart-outline'
      },
      {
        title: 'Respeito às pessoas',
        text: 'Respeito à vida e a todas as formas de diversidade. Dentro e fora do ambiente de trabalho, o respeito gera uma atmosfera que propicia o bem estar das pessoas necessário para o bem estar de nossas funções.',
        icon: 'mdi-account-group'
      },
      {
        title: 'Integridade',
        text: 'Somente através da Integridade, sempre galgada pela ética e pela honestidade, será possível criar os verdadeiros laços de confiança e parceria.',
        icon: 'mdi-scale-balance'
      },
      {
        title: 'Responsabilidade',
        text: 'A responsabilidade é o que nos mantém ativos para “fazer acontecer” os compromissos assumidos.',
        icon: 'mdi-shield-account'
      },
      {
        title: 'Melhoria Contínua',
        text: 'A busca incessante pelo aperfeiçoamento dos processos.',
        icon: 'mdi-trending-up'
      },
      {
        title: 'Sustentabilidade',
        text: 'Conciliação entre proteção ambiental e atividades econômicas e sociais, respeito à biodiversidade e Consumo consciente.',
        icon: 'mdi-bee-flower'
      },
    ]
  }),
}
</script>
<style scoped>
.about-container {
  display: flex;
  flex-direction: column;
  gap: 5rem;
  padding: 2rem 1rem;
}
.section-about-p1 {
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
}
.section-imgs-p1 {
  height: 10rem;
  background-position: center;
  background-size: cover;
}
.img-01-p1 {
  background-image: url('@/assets/image/about-img-1.webp');
  background-position: left;
}
.img-02-p1 {
  background-image: url('@/assets/image/about-img-2.webp');
}
.img-03-p1 {
  background-image: url('@/assets/image/about-img-3.webp');
}
.img-04-p1 {
  background-image: url('@/assets/image/about-img-4.webp');
}
.section-about-p2 {
  display: flex;
  flex-direction: column;
}
.cards-business-values {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.section-about-p3 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  text-align: center;
}
.section-about-p3 .section-paragraph {
  text-align: center;
  font-size: 1.2rem;
  font-weight: 500;
}
.partners-paragraph {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.worker-icon {
  color: rgb(113, 10, 10);
}
.section-about-p5 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .cards-business-values {
    flex-direction: row;
    flex-wrap: wrap;
    gap: 1rem;
  }
  .card-business-item {
    width: 48%;
  }
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
  .section-imgs-p1 {
    height: 15rem;
  }
  .section-about-p3 {
    background-image: url('@/assets/image/project-bg.webp');
    background-size: cover;
    background-position: bottom;
    flex-direction: row;
    padding: 8rem 2rem;
  }
  .section-p3-mission {
    width: 50%;
  }
  .section-p3-vision {
    width: 50%;
  }
  .section-about-p5 {
    margin-bottom: 3rem;
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