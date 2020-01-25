<template>
  <div class="container">
    <Header />
    <main>main</main>
    <footer>footer</footer>
  </div>
</template>

<script lang="ts">
import { createComponent } from '@vue/composition-api'
import Header from '@/components/Header.vue'

export default createComponent({
  components: {
    Header
  }
})
</script>

<style lang="scss"></style>
