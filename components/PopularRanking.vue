<template>
  <section>
    <ArticleLIstView
      v-for="(article, index) in articles"
      :key="index"
      :article="article"
      :rank="index + 1"
    />
  </section>
</template>

<script lang="ts">
import { createComponent, ref } from '@vue/composition-api'
import ArticleLIstView from '@/components/ArticleLIstView.vue'

type Article = {
  title: string
  articleURL: string
  articleImage: string
  writerImage: string
  writerName: string
  updateTime: string
  viewNum: string
  tags: string[]
}

export default createComponent({
  components: {
    ArticleLIstView
  },
  // eslint-disable-next-line prettier/prettier
  setup () {
    const articles = ref<Article[]>([
      {
        title: `ふりかえ鉄板おすすめ人気ランキング10選
        【ごはん検定特Aライターが厳選！話題の商品紹介も】`,
        articleURL: 'https://smashop.jp/subcategory/403700/special',
        articleImage: '/img/hurikake2.jpg',
        writerImage: '/img/writer.jpg',
        writerName: '実用書ライター：小田原',
        updateTime: '1時間前',
        viewNum: '000,000',
        tag: ['徹底比較', '専門家']
      },
      {
        title: `【徹底比較】カップラーメン鉄板おすすめランキング10選
        【商品を購入して食べ比べました】`,
        articleURL: 'https://smashop.jp/subcategory/404000/special',
        articleImage: '/img/cup-noodle.jpg',
        writerImage: '/img/writer.jpg',
        writerName: '実用書ライター：小田原',
        updateTime: '1時間前',
        viewNum: '000,000',
        tag: ['徹底比較', '専門家']
      },
      {
        title: `【徹底比較】発泡酒鉄板おすすめランキング11選
        【糖質あり・なし人気商品を購入して飲み比べ検証】`,
        articleURL: 'https://smashop.jp/subcategory/603030/special',
        articleImage: '/img/beer.jpg',
        writerImage: '/img/writer.jpg',
        writerName: '実用書ライター：小田原',
        updateTime: '1時間前',
        viewNum: '000,000',
        tag: ['徹底比較', '専門家']
      }
    ])

    return {
      articles
    }
  }
})
</script>
