<template>
  <div :style="styleObject">
    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Laudantium ipsum totam voluptate
    corporis quaerat molestiae qui consectetur ratione debitis cum, beatae delectus. Fugit, sit.
    Vero quaerat beatae neque voluptas inventore.
  </div>
  <button @click="fontSize--">-</button>
  <button @click="fontSize++">+</button>
</template>

<script>
import { computed, reactive, ref } from 'vue'

export default {
  setup() {
    const fontSize = ref(13)
    // 얘는 마운트 될때만 딱 한번 적용됨
    // const styleObject = reactive({
    //   color: 'red',
    //   fontSize: fontSize.value + 'px',
    // })
    const styleObject = computed(() => ({
      color: 'red',
      fontSize: fontSize.value + 'px',
    }))
    return { styleObject, fontSize }
  },
}
</script>

<style lang="scss" scoped></style>
