<template>
  <HeaderPage :header-image="headerImage" :header-title="headerTitle" />
  <div class="contact-container">
    <div class="section-contact-p1">
      <SectionTitle :main-title="'Queremos te ouvir'" :sub-title="'Compartilhe seu sonho'" />
      <div class="section-paragraph">
        <p>
          Estamos sempre abertos a novas ideias, projetos e conexões. Se você tem um empreendimento em mente, deseja
          iniciar uma parceria ou simplesmente quer deixar seu feedback, este é o espaço certo. Envie sua mensagem e fale
          diretamente com a equipe da B2 Engenharia & Construção — será um prazer ouvir você e encontrar caminhos juntos
          para transformar oportunidades em realizações concretas.
        </p>
      </div>
    </div>
    <ContactForm />
  </div>
</template>
<script>
import ContactForm from '@/components/ContactForm.vue';
import HeaderPage from '@/components/HeaderPage.vue';
import SectionTitle from '@/components/SectionTitle.vue';

export default {
  name: 'ContactView',
  components: {
    ContactForm,
    HeaderPage,
    SectionTitle
  },
  data: () => ({
    headerImage: require("@/assets/image/contact-header.webp"),
    headerTitle: 'Fale conosco'
  }),
}
</script>
<style scoped>
.contact-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin: 4rem auto;
}
.section-contact-p1 {
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
  .contact-container {
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
  .contact-container {
    max-width: 1200px;
  }
}
</style>