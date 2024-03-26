<template>
  <!-- <GreetMe name="Milan" />
  <GreetMe :name="name" :email="email" /> -->

  <ArticleList title="Article" :likes="50" :isPublished="true" />
</template>

<script>
// import GreetMe from './components/Greet.vue'
import ArticleList from './components/Article.vue'

export default {
  name: 'App',
  components: {
    // GreetMe,
    ArticleList
  },
  data() {
    return {
      name: 'milosh',
      email: 'milosh@gmail.com'
    }
  }
}
</script>

<style></style>
