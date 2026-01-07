<script setup lang="ts">
import { RouterView } from 'vue-router'
import HeaderNav from './components/HeaderNav.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <HeaderNav />
  <main>
    <RouterView />
  </main>
  <FooterSection />
</template>

<style scoped>
main {
  flex: 1;
  width: 100%;
}
</style>
