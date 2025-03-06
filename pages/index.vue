<script setup>
const { data: articles } = await useAsyncData('articles', () =>
  queryContent().find()
)
</script>

<template>
  <div>
    <h1>Il mio Blog</h1>
    <ul>
      <li v-for="article in articles" :key="article._path">
        <NuxtLink :to="article._path">{{ article.title }}</NuxtLink>
      </li>
    </ul>
  </div>
</template>
