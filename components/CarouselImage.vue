<template>
  <a
    class="carousel-image-wrapper"
    :href="article.articleURL"
    :style="{ backgroundImage: 'url(' + article.articleImage + ')' }"
  >
    <div class="article-image">
      <p class="article-title">
        {{ article.title }}
      </p>
      <div class="article-row">
        <div class="writer-wrapper">
          <img class="writer-image" :src="article.writerImage" />
          <span class="writer-name">{{ article.writerName }}</span>
        </div>
        <div class="article-info-wrapper">
          <span>{{ article.updateTime }}</span>
          <span>{{ article.viewNum }} views</span>
        </div>
      </div>
    </div>
  </a>
</template>

<script lang="ts">
import { createComponent } from '@vue/composition-api'

type CarouselArticle = {
  title: string
  articleURL: string
  articleImage: string
  writerImage: string
  writerName: string
  updateTime: string
  viewNum: string
}
export default createComponent({
  props: {
    article: {
      type: Object as () => CarouselArticle,
      default: {}
    }
  },
  // eslint-disable-next-line prettier/prettier
  setup (props) {
    return props.article
  }
})
</script>

<style lang="scss" scoped>
.carousel-image-wrapper {
  display: flex;
  align-items: flex-end;
  margin-right: 1rem;
  height: 12rem;
  min-width: 17rem;
  box-shadow: 0.2rem 0.2rem 10px rgba(0, 0, 0, 0.6),
    inset 0 -6rem 2rem rgba(0, 0, 0, 0.6);
  background-size: cover;
  text-decoration: none;
  border-radius: 0.6rem;

  .article-image {
    display: grid;
    padding: 0.6rem;
    color: white;

    .article-title {
      grid-row: 1;
      margin-bottom: 0.4rem;
      font-size: 0.8rem;
      font-weight: bold;
    }

    .article-row {
      display: flex;
      justify-content: space-between;

      .writer-wrapper {
        display: flex;
        align-items: center;

        .writer-image {
          margin-right: 0.2rem;
          width: 2rem;
          border-radius: 50%;
        }

        .writer-name {
          font-size: 0.6rem;
          font-weight: bold;
        }
      }

      .article-info-wrapper {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        font-size: 0.6rem;
      }
    }
  }
}
</style>
