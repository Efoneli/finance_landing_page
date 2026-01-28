<template>
  <div>
    <NavBar />
    <main>
      <NuxtPage />
    </main>
    <ScrollProgress />
  </div>
</template>

<script setup lang="ts">
useHead({
  titleTemplate: '%s - Staco',
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ]
})
</script>