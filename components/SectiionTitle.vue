<template>
  <section class="orange-section">
    <h2 class="section-title">
      {{ section.title }}
    </h2>
    <h3 class="section-comment">
      {{ section.comment }}
    </h3>
  </section>
</template>

<script lang="ts">
import { createComponent } from '@vue/composition-api'

type Section = {
  title: string
  comment: string
}

export default createComponent({
  props: {
    section: {
      type: Object as () => Section,
      default: {}
    }
  },
  // eslint-disable-next-line prettier/prettier
  setup (props) {
    return props.section
  }
})
</script>

<style lang="scss">
.orange-section {
  padding: 1.5rem 1rem 0.2rem;
  border-bottom: 4px solid orange;

  .section-title {
    font-size: 1.2rem;
  }

  .section-comment {
    font-weight: 600;
    color: gray;
    font-size: 0.8rem;
  }
}
</style>
