<template>
  <div class="carousel-wrapper">
    <CarouselImage
      v-for="(article, index) in articles"
      :key="index"
      :article="article"
    />
  </div>
</template>

<script lang="ts">
import { createComponent, ref } from '@vue/composition-api'
import CarouselImage from '@/components/CarouselImage.vue'

type CarouselArticle = {
  title: string
  articleImage: string
  writerImage: string
  writerName: string
  updateTime: string
  viewNum: string
}

export default createComponent({
  components: {
    CarouselImage
  },
  // eslint-disable-next-line prettier/prettier
  setup () {
    const articles = ref<CarouselArticle[]>([
      {
        title: `ふりかえ鉄板おすすめ人気ランキング10選
        【ごはん検定特Aライターが厳選！話題の商品紹介も】`,
        articleImage: '/img/hurikake2.jpg',
        writerImage: '/img/writer.jpg',
        writerName: '実用書ライター：小田原',
        updateTime: '1時間前',
        viewNum: '000,000'
      },
      {
        title: `【徹底比較】カップラーメン鉄板おすすめランキング10選
        【商品を購入して食べ比べました】`,
        articleImage: '/img/cup-noodle.jpg',
        writerImage: '/img/writer.jpg',
        writerName: '実用書ライター：小田原',
        updateTime: '1時間前',
        viewNum: '000,000'
      }
    ])

    return {
      articles
    }
  }
})
</script>

<style lang="scss" scoped>
.carousel-wrapper {
  display: flex;
  padding: 1rem;
  overflow-x: scroll;
}
</style>
