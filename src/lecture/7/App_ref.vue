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
      color: 'red',
      //fontSize: '20px', //다시 메인에서 수정
      fontSize: '12px', //test에서 수정함2
      //fontSize: '17px', //원격 수정
    })

    return { message, addMessage, reactiveMessage, addMessage2, styleObject }
  },
}
</script>

<style lang="scss" scoped></style>
