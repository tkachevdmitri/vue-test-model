<template>
  <div>
    <template v-for="phone in phones" :key="phone">
      <div>
        <input type="text" v-model="phone.number" />
      </div>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: Array,
  },
  emits: ['update:modelValue'],
  data() {
    return {
      phones: this.modelValue,
    }
  },
}
</script>
