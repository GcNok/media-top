<template>
  <main>
    <SectiionTitle :section="sections[0]" />
    <Carousel />
    <SectiionTitle :section="sections[1]" />
  </main>
</template>

<script lang="ts">
import { createComponent, ref } from '@vue/composition-api'
import SectiionTitle from '@/components/SectiionTitle.vue'
import Carousel from '@/components/Carousel.vue'

type Section = {
  title: string
  comment: string
}

export default createComponent({
  components: {
    SectiionTitle,
    Carousel
  },
  // eslint-disable-next-line prettier/prettier
  setup () {
    const sections = ref<Section[]>([
      {
        title: '話題の記事',
        comment: 'SS編集部が厳選したおすすめの今すぐ読むべき記事まとめ'
      },
      {
        title: '人気記事ランキング',
        comment: '繰り返し読みたくなる暮らしに役立つ記事をご紹介'
      }
    ])
    return {
      sections
    }
  }
})
</script>
