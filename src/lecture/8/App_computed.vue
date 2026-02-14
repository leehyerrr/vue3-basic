<template>
  <!-- <div>{{ teacher.lectures.length > 0 ? '있음' : '없음' }}</div> -->
  <div>{{ hasLecture }}</div>
  <div>{{ existLecture() }}</div>
  <div>{{ count }}</div>
  <button @click="count++">증가</button>
  <div>{{ fullName }}</div>
</template>

<script>
import { computed, reactive, ref } from 'vue'

export default {
  setup() {
    const teacher = reactive({
      name: '짐코딩',
      lectures: ['Html', 'javascript', 'vue3'],
    })

    const hasLecture = computed(() => {
      console.log('computed')
      return teacher.lectures.length > 0 ? '있음' : '없음'
    })
    const existLecture = () => {
      console.log('method')
      return teacher.lectures.length > 0 ? '있음' : '없음'
    }

    const count = ref(0)

    const firstName = ref('홍')
    const lastName = ref('길동')

    // const fullName = computed(() => firstName.value + ' ' + lastName.value)
    const fullName = computed({
      get() {
        return firstName.value + ' ' + lastName.value
      },
      set(value) {
        // console.log(value.split(' '))
        ;[firstName.value, lastName.value] = value.split(' ')
      },
    })
    fullName.value = 'new name'
    return { teacher, hasLecture, existLecture, count, fullName }
  },
}
</script>

<style lang="scss" scoped></style>
