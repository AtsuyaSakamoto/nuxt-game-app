<template>
  <div>
    {{ text }}
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const text = 'Hello, World!'

    return {
      text,
    }
  },
})
</script>

<style lang="scss" scoped>
// div {
//   background-color: blue;
// }
</style>
