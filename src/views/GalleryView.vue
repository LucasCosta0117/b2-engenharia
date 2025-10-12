<template>
  <HeaderPage 
    :header-image="headerImage"
    :header-title="headerTitle"
  />
  <v-container class="gallery-container">
    <SectionTitle class="section-title" :main-title="sectionTitle.mainTitle"
      :sub-title="sectionTitle.subTitle" />
    <div class="card-gallery-container">
      <CardGallery
        v-for="card of cardsGalleryList" :key="card.title"
        :title="card.title"
        :thumb-url="card.thumbUrl"
        :feature="card.feature"
        :website="card.website"
        @click = "openModal(card)"
      />
    </div>
    <ModalGallery
      v-model:show-modal="showModal"
      :project="selectedProject"
    />
  </v-container>
</template>
<script>
import HeaderPage from '@/components/HeaderPage.vue';
import CardGallery from '@/components/CardGallery.vue';
import SectionTitle from '@/components/SectionTitle.vue';
import ModalGallery from '@/components/ModalGallery.vue';

export default {
  name: 'GalleryView',
  components: {
    HeaderPage,
    CardGallery,
    SectionTitle,
    ModalGallery
  },
  data: () => ({
    headerImage: require("@/assets/image/gallery-header.webp"),
    headerTitle: 'Nossos empreendimentos',
    sectionTitle: {
      mainTitle: 'Galeria',
      subTitle: 'Lançamentos e Entregas'
    },
    cardsGalleryList: [
      {
        title: 'Ilhéus Select',
        thumbUrl: require('@/assets/image/card_gallery/ilheus-img.webp'),
        feature: {
          bedrooms: '2, 3 e 4 suítes',
          area: '50m²',
          city: 'Ilhéus - BA',
          launch: '2026'
        },
        website: 'https://www.ilheusselect.com.br/',
        imgs: [
          require('@/assets/image/modal-imgs/ilheus-select/select-1.webp'),
          require('@/assets/image/modal-imgs/ilheus-select/select-2.webp'),
          require('@/assets/image/modal-imgs/ilheus-select/select-3.webp'),
          require('@/assets/image/modal-imgs/ilheus-select/select-4.webp'),
          require('@/assets/image/modal-imgs/ilheus-select/select-5.webp'),
          require('@/assets/image/modal-imgs/ilheus-select/select-6.webp'),
          require('@/assets/image/modal-imgs/ilheus-select/select-7.webp'),
          require('@/assets/image/modal-imgs/ilheus-select/select-8.webp'),
          require('@/assets/image/card_gallery/ilheus-img.webp')
        ]
      },
      {
        title: 'Mamanuca',
        thumbUrl: require('@/assets/image/card_gallery/mamanuca-img.webp'),
        feature: {
          bedrooms: '1 quarto', 
          area: '35m²',
          city: 'Praia do Forte - BA',
          launch: '2026'
        },
        website: 'https://vivermamanuca.com.br/',
        imgs: [
          require('@/assets/image/modal-imgs/mamanuca/mamanuca-1.webp'),
          require('@/assets/image/modal-imgs/mamanuca/mamanuca-2.webp'),
          require('@/assets/image/modal-imgs/mamanuca/mamanuca-3.webp'),
          require('@/assets/image/modal-imgs/mamanuca/mamanuca-4.webp'),
          require('@/assets/image/card_gallery/mamanuca-img.webp')
        ]
      },
      {
        title: 'Recanto das Bromélias',
        thumbUrl: require('@/assets/image/card_gallery/bromelia.webp'),
        feature: {
          bedrooms: '2 quartos', 
          area: '50m²',
          city: 'Imbassaí - BA',
          launch: '2023'
        },
        website: '',
        imgs: [
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-01.webp'),
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-02.webp'),
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-03.webp'),
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-04.webp'),
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-05.webp'),
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-06.webp'),
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-07.webp'),
          require('@/assets/image/modal-imgs/bromelias/Recanto-da-Bromelias-08.webp'),
        ]
      },
      {
        title: 'Chácara do Açu',
        thumbUrl: require('@/assets/image/card_gallery/chacara-do-acu.webp'),
        feature: {
          bedrooms: '2 quartos', 
          area: '50m²',
          city: 'Açu da Tôrre - BA',
          launch: '2022'
        },
        website: '',
        imgs: [
          require('@/assets/image/modal-imgs/chacara-acu/Chacara-do-Acu-1.webp'),
          require('@/assets/image/modal-imgs/chacara-acu/Chacara-do-Acu-2.webp'),
        ]
      },
      {
        title: 'Costa do Mar',
        thumbUrl: require('@/assets/image/card_gallery/costa-do-mar.webp'),
        feature: {
          bedrooms: '1 quarto', 
          area: '50m²',
          city: 'Praia do Forte - BA',
          launch: '2021'
        },
        website: '',
        imgs: [
          require('@/assets/image/modal-imgs/costa-mar/Costa-do-Mar-1.webp'),
          require('@/assets/image/modal-imgs/costa-mar/Costa-do-Mar-2.webp'),
          require('@/assets/image/modal-imgs/costa-mar/Costa-do-Mar-3.webp'),
        ]
      },
      {
        title: 'Fort de Ville',
        thumbUrl: require('@/assets/image/card_gallery/fort-de-ville.webp'),
        feature: {
          bedrooms: '2 quartos', 
          area: '50m²',
          city: 'Praia do Forte - BA',
          launch: '2021'
        },
        website: '',
        imgs: [
          require('@/assets/image/modal-imgs/fort-ville/Fort-de-Ville-1.webp'),
          require('@/assets/image/modal-imgs/fort-ville/Fort-de-Ville-2.webp'),
          require('@/assets/image/modal-imgs/fort-ville/Fort-de-Ville-3.webp'),
          require('@/assets/image/modal-imgs/fort-ville/Fort-de-Ville-4.webp'),
          require('@/assets/image/modal-imgs/fort-ville/Fort-de-Ville-5.webp'),
        ]
      },
    ],
    showModal:false,
    selectedProject: {}
  }),
  methods: {
    openModal(proj) {
      this.showModal = true;
      this.selectedProject = proj;
    }
  }
}
</script>
<style scoped>
.gallery-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  background-image: url('@/assets/image/building.webp');
  background-size: cover;
}
.card-gallery-container {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .card-gallery-container {
    flex-direction: row;
    flex-wrap: wrap;
    gap: 1rem;
  }
  .card-gallery-container .card-container{
    width: 47.5%;
  }
}

/**
 * Dispositivos médios/grandes
 * Vuetify 'md' Break Point
 */
@media (min-width: 960px) {

}

/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1400px) {
  .gallery-container {
    max-width: 1300px;
  }
}
</style>