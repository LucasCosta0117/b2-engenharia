<template>
  <v-carousel v-model="currentSlide" cycle :interval="4000" :show-arrows="false" delimiter-icon="mdi-square"
    height="100vh">
    <v-carousel-item v-for="(image, i) in images" :key="i" :src="image.path" cover class="zoom-in" />
    <v-container class="caption-container">
      <h2 class="caption-text">{{ images[currentSlide].caption }}</h2>
    </v-container>
  </v-carousel>
  <v-container class="home-container">
    <SectionTitle :title="'A Empresa'"></SectionTitle>
    <section class="home-section">
      <div>
        A B2 Engenharia & Construção é uma empresa que nasceu com o intuito de viabilizar empreendimentos a partir do
        pleno entendimento do cenário de mercado e das variáveis que vão garantir o seu sucesso. Deste modo, sempre
        respeitando o sonho dos nossos parceiros, buscamos influenciá-los de forma sustentável, com base na experiência
        dos nossos profissionais nas mais variadas obras de grande porte.
      </div>
      <div>
        Um dos focos da nossa atuação é a Incorporação Imobiliária para projetos comerciais e residenciais, desde a fase
        de concepção e aprovação, até a execução. Para projetos que dependem de recursos financeiros, fazemos toda a
        captação para garantir a implantação do empreendimento.
      </div>
      <div>
        A B2 conta com seu conhecimento do mercado para desenvolver projetos inteligentes e sob medida para os diversos
        públicos e regiões, pautada sempre em sua política de Compliance e atuando com uma gestão ativa nos
        empreendimentos, a fim de mitigar os riscos e maximizar os ganhos.
      </div>
    </section>
  </v-container>
</template>
<script>
import SectionTitle from '@/components/SectionTitle.vue';

export default ({
  name: 'HomeView',
  components: {
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
.home-section {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  margin-top: 2rem;
  font-size: 1rem;
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
 * Dispositivos médios/grandes
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