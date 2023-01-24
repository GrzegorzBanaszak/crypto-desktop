<script setup lang="ts">
import ContentNav from "./ContentNav.vue";
import ContentBalance from "./ContentBalance.vue";
import ContentSummery from "./ContentSummery.vue";
import ContentTabs from "./ContentTabs.vue";
</script>

<template>
  <main className="main-container">
    <ContentNav />
    <ContentBalance />
    <ContentSummery />
    <ContentTabs />
  </main>
</template>

<style scoped lang="scss">
.main {
  &-container {
    margin: 1rem 3rem 0 3rem;
    display: grid;
    flex-grow: 1;
    gap: 1rem;
    grid-template-rows: repeat(7, 1fr);
    grid-template-columns: repeat(2, 1fr);
    grid-template-areas:
      "nav nav"
      "balance summary"
      "balance summary"
      "balance summary"
      "tabs tabs"
      "tabs tabs"
      "tabs tabs";
  }
}
</style>
