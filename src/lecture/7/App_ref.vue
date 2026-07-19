<template>
  <div :style="styleObject">{{ message }}</div>
  <div>{{ reactiveMessage.xx }}</div>
  <button @click="addMessage">click add</button>
  <button @click="addMessage2">click add2</button>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  setup() {
    let message = ref('hello')
    let reactiveMessage = reactive({ value: 'hello', xx: 33 })
    const addMessage = () => {
      message.value = message.value + '!'
    }
    const addMessage2 = () => {
      reactiveMessage.xx = reactiveMessage.xx + '!'
    }

    const styleObject = reactive({
      color: 'navy3', //원격 수정3
      fontSize: '12px', //원격 수정3
    })

    return { message, addMessage, reactiveMessage, addMessage2, styleObject }
  },
}
</script>

<style lang="scss" scoped></style>
