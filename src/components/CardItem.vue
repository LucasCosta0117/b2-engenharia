<template>
  <v-card
    class="mx-auto card-item-container"
    hover
  >
    <v-card-item>
      <div class="card-item-dash"></div>
      <v-card-title class="card-item-title">
        {{ cardTitle }}
      </v-card-title>
    </v-card-item>
    <v-card-text>
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
    }
  }
}
</script>
<style scoped>
.card-item-container {
  height: 8.5rem;
}
.card-item-dash {
  margin-bottom: 1rem;
  border-bottom: 0.125rem solid goldenrod;
  width: 3rem;
}
.card-item-title {
  font-size: 1rem;
}
</style>