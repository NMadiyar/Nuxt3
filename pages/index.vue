<template>
  <nuxt-link to="/test">123</nuxt-link>
  {{ store.count }}
  <button @click="store.increment()">+</button>
  <button @click="store.decrement()">-</button>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import { useCounter } from '~/stores/counter'

export default defineComponent({
  name: 'Index',
  setup() {
    const store = ref(useCounter())
    const res = store.value.count
    const inc = store.value.increment()
    return { res, inc, store }
  },
})
</script>
