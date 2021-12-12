<template>
  <div>
    <Header />
    <h1>クイズページ</h1>
    <h2>第1問</h2>
    <div>
      <div>
        {{ questionText }}
      </div>
      <ul>
        <li>
          <input v-model="select" type="radio" name="q1" value="1" />1.
          ハンター試験編
        </li>
        <li>
          <input v-model="select" type="radio" name="q1" value="2" />2.
          天空闘技場編
        </li>
        <li>
          <input v-model="select" type="radio" name="q1" value="3" />3.
          ヨークシン編
        </li>
        <li>
          <input v-model="select" type="radio" name="q1" value="4" />4.
          グリードアイランド編
        </li>
        <li>
          <input v-model="select" type="radio" name="q1" value="5" />5. 沈黙
        </li>
      </ul>
      <div class="answer-btn" @click="answer">Answer</div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, useRouter } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const questionText = '次のうちで、「一番漫画の話数が多かった」話は？'

    const select = ref<string>('')

    const router = useRouter()
    const answer = () => {
      console.log(select.value)
      // router.push('/result')
      router.push({ path: '/result', query: { answerNum: select.value } })
    }

    return {
      questionText,
      select,
      answer,
    }
  },
})
</script>

<style lang="scss" scoped>
li {
  list-style: none;
}
div {
  .answer-btn {
    margin: 0 auto;
    margin-top: 60px;
    padding-top: 10px;
    height: 35px;
    width: 120px;
    border-radius: 100vh;
    color: white;
    font-weight: 700;
    background-color: dodgerblue;
    text-align: center;
    &:hover {
      cursor: pointer;
      background-color: blue;
    }
  }
}
</style>
