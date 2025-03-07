<template>
  <div class="container">
    <header class="header">
      <h1>My Awesome Blog</h1>
    </header>
    <main>
      <NuxtPage />
    </main>
    <footer class="footer">
      <p>&copy; 2025 My Blog. All rights reserved.</p>
    </footer>
  </div>
</template>

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
</style>
