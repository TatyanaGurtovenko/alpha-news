<template>
  <TheHeader></TheHeader>
  <PageTitle></PageTitle>
  <NewsList></NewsList>
  <TheFooter></TheFooter>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue'
import TheFooter from "@/components/layout/TheFooter.vue";
import NewsList from "@/components/pages/news/NewsList.vue";
import PageTitle from "@/components/layout/PageTitle.vue";
export default {
  name: 'App',
  components: {
    TheHeader,
    TheFooter,
    NewsList,
    PageTitle
  }
}
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";
#app {
  font-family: 'NutitoSans', NutitoSans, sans-serif;
  color: #17171A;
}
.container {
  max-width: 1720px;
  width: 100%;
  padding: 0 15px;
  margin: 0 auto;
}
</style>
