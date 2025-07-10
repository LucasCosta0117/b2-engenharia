<template>
  <v-container>
    <form @submit.prevent="submit">
      <v-text-field
        v-model="name.value.value"
        :counter="20"
        :error-messages="name.errorMessage.value"
        label="Nome"
      ></v-text-field>
  
      <v-text-field
        v-model="phone.value.value"
        :counter="11"
        :error-messages="phone.errorMessage.value"
        label="Telefone"
        placeholder="(71)99728-4770"
      ></v-text-field>
  
      <v-text-field
        v-model="email.value.value"
        :error-messages="email.errorMessage.value"
        label="E-mail"
        placeholder="contato@email.com"
      ></v-text-field>
  
      <v-row>
        <v-col>
          <v-text-field
            v-model="city.value.value"
            :counter="20"
            :error-messages="city.errorMessage.value"
            label="Cidade"
          ></v-text-field>
        </v-col>
        <v-col>
          <v-select
            v-model="state.value.value"
            :error-messages="state.errorMessage.value"
            :items="listOfStates"
            label="Estado"
          ></v-select>
        </v-col>
      </v-row>
      <v-textarea
        class="message-area"
        v-model="message.value.value"
        :counter="300"
        :error-messages="message.errorMessage.value"
        label="Mensagem"
        placeholder="Compartilhe seu sonho ou envie sua avaliação"
      ></v-textarea>
      <v-row justify="space-around">
          <v-btn
            type="submit"
            class="btn-submit-form"
          >
            Enviar
          </v-btn>
          <v-btn 
            class="btn-clear-form"
            @click="handleReset"
          >
            Limpar
          </v-btn>
      </v-row>
    </form>
  </v-container>
</template>
<script>
import { ref } from 'vue'
import { useField, useForm } from 'vee-validate'
import emailjs from 'emailjs-com'

/**
 * Cria o Formulário de Contato para captação de leads,
 * e impões validações simples para os valores digitados.
 */
export default {
  name: 'ContactForm',
  setup() {
    const { handleSubmit, handleReset } = useForm({
      validationSchema: {
        name: value => value?.length >= 2 || 'O Nome precisa ter pelo menos 2 caracteres.',
        phone: value => /^[0-9-]{11,}$/.test(value) || 'O Número precisa ter pelo menos 11 dígitos (Incluindo o DDD e sem espaços).',
        email: value => /.+@.+\..+/.test(value) || 'E-mail fornecido não é válido.',
        city: value => value?.length >= 2 || 'A Cidade precisa ter pelo menos 2 caracteres.',
        state: value => !!value || 'Selecione um Estado.',
        message: value => value?.length <= 300 || 'Mensagem muito longa, reduza para 300 caracteres.',
      }
    })

    const name = useField('name')
    const phone = useField('phone')
    const email = useField('email')
    const city = useField('city')
    const state = useField('state')
    const message = useField('message')
    const listOfStates = ref([
      'Acre',
      'Alagoas',
      'Amapá',
      'Amazonas',
      'Bahia',
      'Ceará',
      'Distrito Federal',
      'Espírito Santo',
      'Goiás',
      'Maranhão',
      'Mato Grosso',
      'Mato Grosso do Sul',
      'Minas Gerais',
      'Pará',
      'Paraíba',
      'Paraná',
      'Pernambuco',
      'Piauí',
      'Rio de Janeiro',
      'Rio Grande do Norte',
      'Rio Grande do Sul',
      'Rondônia',
      'Roraima',
      'Santa Catarina',
      'São Paulo',
      'Sergipe',
      'Tocantins',
    ])

    const submit = handleSubmit(values => {
      const serviceID = import.meta.env.VUE_APP_EMAILJS_SERVICE_ID
      const templateID = import.meta.env.VUE_APP_EMAILJS_TEMPLATE_ID
      const publicKey = import.meta.env.VUE_APP_EMAILJS_PUBLIC_KEY

      const now = new Date()
      const dateFormated = `${now.getDate()}/${now.getMonth()}/${now.getFullYear()} - ${now.getHours()}:${now.getMinutes()}`;

      emailjs.send(
        serviceID,
        templateID,
        {
          title: 'Fale Conosco: B2 Engenharia e Construção',
          time: dateFormated,
          name: values.name,
          email: values.email,
          phone: values.phone,
          city: values.city,
          state: values.state,
          message: values.message,
        },
        publicKey
      ).then(response => {
        alert('Mensagem enviada com sucesso!', response);
      }).catch(error => {
        alert('Erro ao enviar: ' + error.text);
      });
    })

    return {
      name,
      phone,
      email,
      city,
      state,
      message,
      listOfStates,
      submit,
      handleReset
    }
  }
}
</script>
<style scoped>
.message-area {
  margin-bottom: 1.5rem;
}
.btn-submit-form {
  background-color: rgb(113, 10, 10);
  color: white;
}
.btn-clear-form {
  background-color: rgb(210, 210, 210);
}

/**
 * Pequenos dispositivos
 * Vuetify 'sm' Break Point
 */
@media (min-width: 600px) {
  .btn-submit-form {
    min-width: 12rem;
  }
  .btn-clear-form {
    min-width: 12rem;
  }
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