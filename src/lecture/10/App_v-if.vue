<template>
  <div v-if="visible">hello</div>
  <div v-else>false입니다.</div>
  <button @click="visible = !visible">toggle</button>
  <hr />

  <button @click="type = 'A'">A</button>
  <button @click="type = 'B'">B</button>
  <button @click="type = 'C'">C</button>
  <div v-if="type === 'A'">A입니다.</div>
  <div v-else-if="type === 'B'">B입니다.</div>
  <div v-else>C입니다.</div>
  <hr />

  <template v-if="visible">
    <div>xxx</div>
  </template>
  <hr />

  <h1 v-show="show">title</h1>
  <button @click="show = !show">show toggle</button>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const visible = ref(true)
    const type = ref('A')
    const show = ref(true)
    return { visible, type, show }
  },
}
</script>

<style lang="scss" scoped></style>
