<template>
  <div>
    <h1>게시글</h1>
    <router-link :to="{name:'create'}">작성</router-link>
    <ArticleItem v-for="article in articles"
    :key="article.id"
    :article = article 
    />
  </div>
</template>

<script>
import ArticleItem from '@/components/ArticleItem'
export default {
  name:'IndexView',
  components: {
    ArticleItem
  },
  computed: {
    articles(){
      return this.$store.state.articles
    }
  }
}
</script>

<style>

</style>