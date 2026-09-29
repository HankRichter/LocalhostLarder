<script setup lang="ts">
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';

</script>

<template>
  <div>
    <AppHeader />
    <main class="app-main">
      <NuxtPage />
    </main>
    <AppFooter />
  </div>
</template>

<style>
.app-main {
  padding-bottom: 4.5rem;
}

@media (min-width: 1024px) {
  .app-main {
    padding-bottom: 0;
  }
}
</style>
