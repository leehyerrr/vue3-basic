<template>
  <div>
    <input type="text" :disabled="xx" v-bind="attr" />
    <h2>{{ message.split('').reverse().join('') }}</h2>
    <h2>{{ xx ? 'yes' : 'no' }}</h2>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const test = ref('Hello, Vue 3 with Composition API!')
    const message = ref('안녕하세요')
    const xx = ref(false)
    const attr = ref({
      type: 'password',
      value: '1234',
    })
    return { test, xx, attr, message }
  },
}
</script>

<style lang="scss" scoped></style>
