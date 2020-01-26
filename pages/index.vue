<template>
  <main>
    <SectiionTitle :section="sections[0]" />
    <Carousel />
    <SectiionTitle :section="sections[1]" />
    <PopularRanking />
    <button class="scroll-top-button">
      <i class="material-icons icon-arrow">keyboard_arrow_up</i>
    </button>
  </main>
</template>

<script lang="ts">
import { createComponent, ref } from '@vue/composition-api'
import SectiionTitle from '@/components/SectiionTitle.vue'
import Carousel from '@/components/Carousel.vue'
import PopularRanking from '@/components/PopularRanking.vue'

type Section = {
  title: string
  comment: string
}

export default createComponent({
  components: {
    SectiionTitle,
    Carousel,
    PopularRanking
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

<style lang="scss" scoped>
.scroll-top-button {
  position: fixed;
  bottom: 1.8rem;
  right: 1.8rem;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 3rem;
  height: 3rem;
  color: white;
  background-color: rgba(141, 195, 63, 0.95);
  border-radius: 50%;
  box-shadow: 0.2rem 0.2rem 10px rgba(0, 0, 0, 0.6);

  .icon-arrow {
    font-size: 2.5rem;
  }
}
</style>
