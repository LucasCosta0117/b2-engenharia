<template>
  <v-list class="d-flex flex-row bg-transparent">
    <v-list-item
      v-for="social in socialIcons"
      :key="social.icon"
    >
      <a :href="social.link" target="_blank">
        <v-icon 
          :size="sizeIcon" 
          :color="colorIcon"
          :icon="social.icon" 
          :title="social.title"
        />
      </a>
    </v-list-item>
  </v-list>
</template>
<script>
export default {
  name: 'SocialMidiaList',
  props: {
    /**
     * Define o tamanho do icone pela prop 'size'
     */
    sizeIcon: {
      type: Number,
      default: 32
    },
    /**
     * Define a cor do icone pela prop 'color'
     */
    colorIcon: {
      type: String,
      default: '#ffffff'
    }
  },
  data:() => ({
    socialIcons: [
      {
        icon: 'mdi-instagram',
        title: 'Instagram',
        link: 'https://www.instagram.com/b2.engenhariaeconstrucao'
      },
      {
        icon: 'mdi-whatsapp',
        title: 'Whatsapp',
        link: 'https://wa.me/+5571997284770'
      },
      {
        icon: 'mdi-email',
        title: 'Email',
        link: 'mailto:contato@b2engenhariaeconstrucao.com.br'
      }
    ]
  }),
}
</script>
<style scoped>

</style>