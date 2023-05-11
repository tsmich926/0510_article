<template>
  <div>
    <h1>상세</h1>
    <p>글번호:{{article.id}}</p>
    <p>글제목:{{article.title}}</p>
    <p>글내용:{{article.content}}</p>
    <p>글시간:{{article.createdAt}}</p>

    <button @click="deleteArticle">삭제</button>
    <router-link :to="{name:'index'}">뒤로가기</router-link>
  </div>
</template>

<script>
export default {
  name:'DetailView',
  data(){
    return {
      article:null
    }
  },
  methods:{
    deleteArticle(){
      this.$store.commit('DELETE_ARTICLE',this.article.id)
      this.$router.push({name:'index'})
    }
  },
  computed:{
    articles(){
      return this.$store.state.articles
    }
  },
  created(){
    const getId = this.$route.params.id
    for (const article of this.articles){
      if (article.id === Number(getId) ){
        this.article = article
        break
      }
    }
    if (!this.article){
      this.$router.push({name:"NotFound404"})
    } 
    
  }
}
</script>

<style>

</style>