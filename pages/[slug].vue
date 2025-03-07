<template>
  <div class="prose mx-auto">
    <h1>{{ post.title }}</h1>
    <p class="text-gray-500">{{ post.date }}</p>
    <ContentDoc />
  </div>
</template>

<script setup>
const { params } = useRoute();
const { data: post } = await useAsyncData(params.slug, () => queryContent(`/stories/${params.slug}`).findOne());
</script>