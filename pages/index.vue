<template>
  <div>
    <Header />

    <div class="top">
      <div class="bg-image"></div>
      <div class="start-btn" @click="goQuiz">
        {{ text }}
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, useRouter } from '@nuxtjs/composition-api'
import Header from '../components/Header.vue'

export default defineComponent({
  components: { Header },
  setup() {
    const text: string = 'START'

    const router = useRouter()
    const goQuiz = () => {
      router.push('/quiz')
    }

    return {
      text,
      goQuiz,
    }
  },
})
</script>

<style lang="scss" scoped>
.top {
  height: 900px;
  widows: 100%;
  background-color: pink;
}
div {
  .bg-image {
    height: 150px;
    width: 340px;
    margin: 0 auto;
    margin-top: 20px;
    background-image: url('/hunter.png');
    background-repeat: no-repeat;
    opacity: 1;
    background-color: pink;
  }
  .start-btn {
    margin: 0 auto;
    margin-top: 60px;
    padding-top: 10px;
    height: 35px;
    width: 120px;
    border-radius: 100vh;
    color: white;
    font-weight: 700;
    background-color: skyblue;
    text-align: center;
    &:hover {
      cursor: pointer;
      background-color: blue;
    }
  }
}
</style>
