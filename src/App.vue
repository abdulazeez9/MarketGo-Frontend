<script setup lang="ts">
import NavBar from './components/layout/NavBar.vue'

const maintenance = true 
</script>

<template>
  <div
    v-if="maintenance"
    class="min-h-screen flex flex-col items-center justify-center text-center px-4 bg-background"
  >
    <h1 class="text-3xl font-bold text-heading mb-3">We'll be right back</h1>
    <p class="text-text-muted max-w-md">
      MarketGo is currently undergoing maintenance. Please check back soon.
    </p>
  </div>

  <div v-else class="flex flex-col min-h-screen">
    <NavBar />
    <main class="flex-1">
      <RouterView />
    </main>
  </div>
</template>

<style scoped></style>
