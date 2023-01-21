<script setup lang="ts">
import LogoIcon from "../icons/LogoIcon.vue";
import SideBarNav from "../components/SidebarNav.vue";
</script>

<template>
  <aside className="sidebar-container">
    <h1 className="sidebar-logo"><LogoIcon /> Payte</h1>
    <SideBarNav />
  </aside>
</template>

<style lang="scss">
.sidebar {
  &-container {
    background-color: #f7f7f9;
    width: 15%;
    padding: 1rem;
  }

  &-logo {
    display: flex;
    align-items: center;
    font-weight: 600;
    gap: 0.7rem;
    padding: 0 0.4rem;
  }
}
</style>
