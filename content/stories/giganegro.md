---
title: "Le avventure del Giganegro"
description: "Un racconto epico"
date: "2025-03-07"
---

# Il Giganegro

C'era una volta un eroe leggendario...

// 5. Crea una pagina dinamica per visualizzare le storie
// pages/stories/[slug].vue
<template>
  <div class="prose mx-auto">
    <h1>{{ story.title }}</h1>
    <p class="text-gray-500">{{ story.date }}</p>
    <ContentDoc />
  </div>
</template>

<script setup>
const { params } = useRoute();
const { data: story } = await useAsyncData(params.slug, () => queryContent(`/stories/${params.slug}`).findOne());
</script>