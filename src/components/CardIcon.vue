<template>
  <v-card
    class="mx-auto card-item-container"
    hover
  >
    <v-icon class="card-item-icon" :icon="cardIcon" />
    <v-card-item>
      <v-card-title class="card-item-title">
        {{ cardTitle }}
      </v-card-title>
    </v-card-item>
    <v-card-text class="card-item-text">
      {{ cardText }}
    </v-card-text>
  </v-card>
</template>
<script>
/**
 * Cria um card contendo apenas um título e um texto
 */
export default {
  name: 'CardItem',
  props: {
    /**
     * Título a ser exibido do Card
     */
    cardTitle: {
      type: String,
    },
    /**
     * Texto a ser exebido no Card
     */
    cardText: {
      type: String,
    },
    /**
     * Texto a ser exebido no Card
     */
    cardIcon: {
      type: String,
    }
  }
}
</script>
<style scoped>
.card-item-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 18rem;
  padding: 1rem;
}
.card-item-icon {
  margin-top: 1rem;
  font-size: 4rem;
  color: rgb(130,10,10);
}
.card-item-title {
  font-size: 1.2rem;
  font-weight: 600;
}
.card-item-text {
  text-align: center;
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

}
/**
 * Dispositivos grandes
 * Vuetify 'lg' Break Point
 */
@media (min-width: 1400px) {

}
</style>