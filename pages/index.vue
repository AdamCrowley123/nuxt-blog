<template>
  <div class="container">
    <header class="header">
      <h1>My Awesome Blog</h1>
    </header>
    <main>
      <ul>
        <li v-for="post in posts" :key="post._path">
          <NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
          <p>{{ post.description }}</p>
        </li>
      </ul>
    </main>
    <footer class="footer">
      <p>&copy; 2025 My Blog. All rights reserved.</p>
    </footer>
  </div>
</template>

<script setup>
const { data: posts } = await useAsyncData('posts', () => queryContent('/stories').find());
console.log(posts.value); // Debug
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: Arial, sans-serif;
}
.header {
  background: #333;
  color: white;
  padding: 1rem;
  text-align: center;
}
.footer {
  background: #333;
  color: white;
  padding: 1rem;
  text-align: center;
  margin-top: auto;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  margin: 1rem 0;
}
a {
  color: #42b983;
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}
</style>