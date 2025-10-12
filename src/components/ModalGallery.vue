<template>
  <v-dialog v-model="isOpen" class="gallery-modal-container">
    <v-card class="project-modal-card">
      <v-card-title class="d-flex justify-space-between align-center">
        <span>{{ project?.title }}</span>
        <v-btn flat icon @click="close">
          <v-icon>mdi-close</v-icon>
        </v-btn>
      </v-card-title>

      <v-card-text>
        <v-carousel
          hide-delimiter-background
          show-arrows="hover"
          height="280"
          v-if="project?.imgs && project.imgs.length"
        >
          <v-carousel-item
            v-for="(img, i) in project.imgs"
            :key="i"
          >
            <v-img :src="img" cover></v-img>
          </v-carousel-item>
        </v-carousel>
      </v-card-text>

      <v-card-actions>
        <v-btn
          v-if="project?.website"
          :href="project.website"
          target="_blank"
          prepend-icon="mdi-web"
        >
          Visite o Site
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>
<script>
/**
 * Modal/Dialog aberto ao clickar sobre um card de projeto (ProjectCard.vue),
 * este irá apresentar em maiores detalhes as informações sobre o projeto selecionado.
 */
export default {
  name: 'ModalGallery',
  props: {
    /**
     * Flag para controle de exibição do modal/dialog.
     */
    showModal: {
      type: Boolean, 
      default: false 
    },
    /**
     * Informações do projeto 'clickado'.
     */
    project: {
      type: Object, 
      default: null 
    }
  },
  emits: ['update:showModal'],
  computed: {
    /**
     * Responsável por obter e também manipular, de forma indireta, o valor da props 'showModal'.
     */
    isOpen: {
      get() {
        return this.showModal;
      },
      set(val) {
        this.$emit('update:showModal', val);
      }
    }
  },
  methods: {
    /**
     * Fecha o modal/dialog.
     */
    close() {
      this.isOpen = false;
    }
  }
}
</script>
<style scoped>
.gallery-modal-container {
  max-width: 35rem;
  height: 37rem;
}
.gallery-modal-description {
  font-size: 0.875rem;
}
</style>