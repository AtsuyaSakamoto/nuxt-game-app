<template>
  <div class="bg-color">
    <div>
      <nuxt-link to="/rule"> {{ howToPlay }}</nuxt-link>
    </div>
    <div>
      <nuxt-link to="/"> {{ backHome }}</nuxt-link>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const howToPlay = '遊び方'
    const backHome = 'ホームへ戻る'

    return {
      howToPlay,
      backHome,
    }
  },
})
</script>

<style lang="scss" scoped>
.bg-color {
  background-color: yellow;
}
</style>
