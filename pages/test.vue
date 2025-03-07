<template>
  <div>
    <h1>Test Page</h1>
    <ul>
      <li v-for="post in posts" :key="post._path">
        {{ post.title }}
      </li>
    </ul>
  </div>
</template>

<script setup>
const { data: posts } = await useAsyncData('test', () => queryContent().find());
console.log(posts.value);
</script>