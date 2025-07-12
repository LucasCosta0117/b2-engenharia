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
      <div>"Imagens de projetos B2"</div>
    </div>
    <div class="section-about-p2">
      <SectionTitle class="section-title" :main-title="'Nossos Valores'"
        :sub-title="''" />
      <div class="cards-business-values">
        <CardIcon v-for="val in listBusinessValues" :key="val.title" :card-title="val.title" :card-text="val.text" :card-icon="val.icon"/>
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
  gap: 2rem;
}
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
.section-about-p2 {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.cards-business-values {
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