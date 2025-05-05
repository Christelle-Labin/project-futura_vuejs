<script setup>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
import FrontPage from './components/FrontPage.vue'
import ArticleCard from './components/ArticleCard.vue'
</script>

<template>
  <AppHeader />

  <main>
    <FrontPage />
    <ArticleCard />
  </main>

  <AppFooter />
</template>
