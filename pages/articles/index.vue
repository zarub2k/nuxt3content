<script setup>
// const { data: articles } = await useAsyncData('articles', () => queryContent('/articles').only(['title', 'description']).find())
const articles = await queryContent('articles').only(['title', 'description']).find()
console.log('here: ' + JSON.stringify(articles))
</script>

<template>
  <section>
    <div>Articles page</div>
    <div>
      <div v-for="article in articles" :key="article._path">
        <h2>{{ article.title }}</h2>
        <p>{{ article.description }}</p>
        <!-- <ContentRenderer :value="article" /> -->
      </div>
    </div>
  </section>
</template>