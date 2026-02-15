<template>
  <div class="test" :class="{ active: isActive, 'text-danger': hasError }">텍스트 입니다.</div>
  <div :class="classObject">ttt</div>
  <button @click="toggle">toggle</button>
  <button @click="hasError = !hasError">toggleError</button>
  <div :class="[activeClass, errorCalss]">xxxx</div>
  <div :class="[!isActive ? 'aa' : 'bb', errorCalss, classObject]">aaa</div>
</template>

<script>
import { computed, reactive, ref } from 'vue'

export default {
  setup() {
    const isActive = ref(true)
    const hasError = ref(true)
    // const classObject = reactive({
    //   active: isActive,
    //   'text-danger': hasError,
    // })

    const classObject = computed(() => {
      return {
        // active: true && true,
        // 'text-danger': true && false,
        active: isActive.value && true,
        'text-danger': hasError.value && true,
      }
    })

    const activeClass = ref('active')
    const errorCalss = ref('error')

    const toggle = () => {
      isActive.value = !isActive.value
      // return (isActive.value = !isActive.value)
    }
    return { isActive, hasError, toggle, classObject, activeClass, errorCalss }
  },
}
</script>

<style lang="css" scoped>
.test {
  margin-top: 10px;
}
.active {
  color: red;
}
.text-danger {
  background: blue;
}
</style>
