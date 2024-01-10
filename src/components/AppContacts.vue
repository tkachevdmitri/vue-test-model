<template>
  <div>
    <p class="mb-2 font-bold">Контактные лица</p>

    <template v-for="contact in contacts" :key="contact">
      <div>
        <input type="text" v-model="contact.name" />
        <p>Номера телефонов:</p>
        <app-phones v-model="contact.phones"></app-phones>
      </div>
      <br /><br />
    </template>
  </div>
</template>

<script>
import AppPhones from '@/components/AppPhones.vue'

export default {
  props: {
    modelValue: Array,
  },
  emits: ['update:modelValue'],
  data() {
    return {
      contacts: this.modelValue,
    }
  },
  components: {
    AppPhones,
  },
}
</script>
