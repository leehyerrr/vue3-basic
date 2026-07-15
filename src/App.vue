<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.message }}</li>
    </ul>
  </div>
</template>

<script>
import { reactive } from 'vue'

export default {
  setup() {
    const items = reactive([
      { id: 1, message: 'java1' },
      { id: 2, message: 'java2' },
      { id: 3, message: 'java3' },
    ])
    return { items }
  },
}
</script>

<style lang="scss" scoped></style>
