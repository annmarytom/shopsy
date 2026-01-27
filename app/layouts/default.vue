<script setup lang="ts">
import AppHeader from "~/components/common/AppHeader.vue";
import NewsLetter from "~/components/common/NewsLetter.vue";
</script>

<template>
  <div class="app-layout">
    <AppHeader />
    <slot />
    <NewsLetter />
  </div>
</template>
