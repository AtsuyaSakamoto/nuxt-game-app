<template>
  <div>
    <Header />
    <div v-show="answer">正解</div>
    <div v-show="!answer">不正解</div>
    {{ $route.query.answerNum }}
  </div>
</template>

<script lang="ts">
import {
  defineComponent,
  ref,
  onMounted,
  useRoute,
} from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const answer = ref<boolean>(false)
    const route = useRoute()

    onMounted(() => {
      if (route.value.query.answerNum === '4') {
        answer.value = true
      } else {
        answer.value = false
      }

      console.log(route.value.query.answerNum)
    })
    return { answer }
  },
})
</script>

<style lang="scss" scoped></style>
