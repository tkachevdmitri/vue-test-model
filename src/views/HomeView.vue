<template>
  <main>
    <h1 class="text-3xl mb-4">Test</h1>
    <p>model: {{ form }}</p>
    <br /><br />

    <form @submit.prevent="onSubmit">
      <input type="text" v-model="form.name" /><br /><br />
      <textarea v-model="form.description"></textarea>

      <app-contacts v-model="form.contacts"></app-contacts>

      <br /><br />
      <button>Отправить</button>
    </form>
  </main>
</template>

<script>
import AppContacts from '@/components/AppContacts.vue'

export default {
  data() {
    return {
      form: {
        name: 'Название',
        description: 'Описание',
        contacts: [
          {
            name: 'Петя',
            phones: [
              {
                number: '+79803943131',
              },
              {
                number: '+79803943132',
              },
            ],
          },
          {
            name: 'Вася',
            phones: [
              {
                number: '+79803943131',
              },
            ],
          },
        ],
      },
    }
  },
  methods: {
    onSubmit() {
      console.log('Отправляем форму')
      console.log(this.form)
    },
  },
  components: {
    AppContacts,
  },
}
</script>
