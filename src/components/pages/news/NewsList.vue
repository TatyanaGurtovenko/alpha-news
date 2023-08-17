<template>
  <div class="news">
    <div class="container news__container">
      <div class="news__list">
        <NewsCard v-for="item in news" :key="item.code" :news="item"></NewsCard>
      </div>
      <MoreButton @click.prevent="loadMore" v-if="isBtnMore"></MoreButton>
    </div>
  </div>
</template>

<script>
import {onMounted, ref} from 'vue'
import NewsCard from "@/components/pages/news/NewsCard.vue"
import MoreButton from "@/components/ui/buttons/MoreButton.vue";

export default {
  name: 'NewsList',
  components: {NewsCard, MoreButton},
  setup() {
    const news = ref(null)
    const newsNav = ref(null)
    const isBtnMore = ref(false)

    const fetchNews = async (page) => {
      await fetch(`https://flems.github.io/test/api/news/${page}`).then((response) => response.json()).then(data => {
        isBtnMore.value = data.nav.total > data.nav.current
        if (news.value && news.value.length > 0) {
          news.value =  news.value.concat(data.items)
        }
        else {
          news.value = data.items
        }
      })
    }
    const loadMore = async () => {
      await fetchNews(2)
    }
    onMounted(async () => {
      await fetchNews(1)
    })


    return {
      news,
      newsNav,
      fetchNews,
      loadMore,
      isBtnMore
    }
  }
}
</script>

<style scoped lang="scss">
.news__list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 48px;
  row-gap: 64px;
  margin-top: 64px;
  margin-bottom: 72px;
  @media (max-width: 1200px) {
    grid-template-columns: repeat(2, 1fr);
    column-gap: 30px;
    row-gap: 30px;
  }
  @media (max-width: 599px) {
    grid-template-columns: repeat(1, 1fr);
  }
}

.news__container {
  text-align: center;
}
</style>
