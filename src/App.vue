<script setup lang="ts">
import Sidebar from "./components/Sidebar.vue";
import Content from "./components/Content.vue";
</script>

<template>
  <div className="container">
    <Sidebar></Sidebar>
    <Content>main</Content>
  </div>
</template>

<style scoped lang="scss">
.container {
  width: 100%;
  height: 100vh;
  display: flex;
}
</style>
