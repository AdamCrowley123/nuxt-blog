<script setup>
const { params } = useRoute()
const { data: article } = await useAsyncData(`article-${params.slug}`, () =>
  queryContent(params.slug).findOne()
)
</script>

<template>
  <article v-if="article">
    <h1>{{ article.title }}</h1>
    <p>{{ article.description }}</p>
    <ContentRenderer :value="article" />
  </article>
</template>
