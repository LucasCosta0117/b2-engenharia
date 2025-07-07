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
      <v-row justify="space-around">
          <v-btn
            type="submit"
            color="rgb(113, 10, 10)"
          >
            Enviar
          </v-btn>
          <v-btn 
            color="rgb(210, 210, 210)"
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
        phone: value => /^[0-9-]{7,}$/.test(value) || 'O Número precisa ter pelo menos 11 dígitos (Incluindo o DDD e sem espaços).',
        email: value => /^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value) || 'E-mail fornecido não é válido.',
        city: value => value?.length >= 2 || 'A Cidade precisa ter pelo menos 2 caracteres.',
        state: value => !!value || 'Selecione um Estado.',
      }
    })

    const name = useField('name')
    const phone = useField('phone')
    const email = useField('email')
    const city = useField('city')
    const state = useField('state')
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
      //Enviar email para conta da b2.
      alert(JSON.stringify(values, null, 2))
    })

    return {
      name,
      phone,
      email,
      city,
      state,
      listOfStates,
      submit,
      handleReset
    }
  }
}
</script>
<style scoped>
</style>