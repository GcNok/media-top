<template>
  <div class="article-row-wrapper">
    <div class="article-row-left-wrapper">
      <img
        class="article-row-image"
        :src="article.articleImage"
        alt="article"
      />
      <span
        class="raniking-num"
        :class="{ gold: rank === 1, silver: rank === 2, bronze: rank === 3 }"
        >{{ rank }}</span
      >
    </div>
    <div class="article-row-right-wrapper">
      <p class="article-row-title">
        {{ article.title }}
      </p>
      <div class="article-row-info">
        <div class="writer-wrapper">
          <img class="writer-image" :src="article.writerImage" alt="writer" />
          <span class="writer-name">{{ article.writerName }}</span>
        </div>
        <span>{{ article.viewNum }} views</span>
      </div>
      <div class="tag-wrapper">
        <div v-for="(tag, index) in article.tags" :key="index" class="tag">
          #{{ tag }}
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { createComponent, ref } from '@vue/composition-api'

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
  props: {
    article: {
      type: Object as () => Article,
      default: {}
    },
    rank: {
      type: Number,
      default: 0
    }
  },
  // eslint-disable-next-line prettier/prettier
  setup (props) {
    const article = ref<Article>(props.article)
    const rank = ref(props.rank)
    return {
      article,
      rank
    }
  }
})
</script>

<style lang="scss" scoped>
.article-row-wrapper {
  display: flex;
  align-items: center;
  margin-top: 1rem;
  padding: 0.4rem 1rem;
  box-shadow: 0.2rem 0.1rem 10px rgba(0, 0, 0, 0.6);
  border-radius: 0.6rem;

  .article-row-left-wrapper {
    position: relative;

    .article-row-image {
      width: 5rem;
      height: 5rem;
      object-fit: cover;
    }

    .raniking-num {
      position: absolute;
      top: 0.2rem;
      left: 0.2rem;
      display: inline-block;
      width: 1.6rem;
      height: 1.6rem;
      line-height: 1.6rem;
      text-align: center;
      font-size: 0.9rem;
      font-weight: bold;
      color: white;
      border: 1px solid white;
      border-radius: 50%;
    }

    .gold {
      background-color: rgb(255, 208, 0);
    }

    .silver {
      background-color: silver;
    }

    .bronze {
      background-color: brown;
    }
  }

  .article-row-right-wrapper {
    display: flex;
    flex-direction: column;
    margin-left: 1rem;

    .article-row-title {
      font-size: 0.9rem;
      font-weight: bold;
    }

    .article-row-info {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.4rem;

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
        }
      }
    }

    .tag-wrapper {
      display: flex;
      justify-content: start;
      margin-top: 0.3rem;

      .tag {
        padding: 0.2rem 0.4rem;
        margin-right: 0.4rem;
        background-color: rgb(228, 228, 228);
        font-size: 0.6rem;
        border-radius: 0.6rem;
      }
    }
  }
}
</style>
