<template>
  <main class="container">
    <RouterView />
  </main>
</template>

<style>
body {
  margin: 0;
  font-family: system-ui, sans-serif;
  background: #f5f7fa;
  color: #1f2933;
}

.container {
  max-width: 560px;
  margin: 48px auto;
  padding: 0 20px;
}

h1 {
  margin-bottom: 8px;
}

a {
  color: #2b6cb0;
  text-decoration: none;
  padding: 12px;
  border: 1px solid #2b6cb0;
  border-radius: 16px;
  transition: ease-out 250ms;
}
a:hover{
  background-color: #2b6cb0;
  color: white;
}
</style>