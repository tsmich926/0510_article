<template>
  <div @click="goDetail(article.id)">
    <p>제목:{{article.title}}</p>
    <p>내용:{{article.content}}</p>
    <hr>
  </div>
</template>

<script>
export default {
  name:'ArticleItem',
  props:{
    article: Object
  },
  methods:{
    goDetail(id){
      this.$router.push({name:"detail",params:{id:id}})
    }
  }
}
</script>

<style>

</style>