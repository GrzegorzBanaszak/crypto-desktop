<script setup lang="ts">
import LogoIcon from "../icons/LogoIcon.vue";
import SidebarNav from "../components/SidebarNav.vue";
import SidebarFavorites from "../components/SidebarFavorites.vue";
import UserCard from "./UserCard.vue";
</script>

<template>
  <aside className="sidebar-container">
    <h1 className="sidebar-logo"><LogoIcon /> Payte</h1>
    <SidebarNav />
    <SidebarFavorites />
    <UserCard
      :full-name="'Marc Webber'"
      :email="'marc@riot.com'"
      :image-name="'portret.jpg'"
    />
  </aside>
</template>

<style lang="scss">
.sidebar {
  &-container {
    background-color: #f7f7f9;
    width: 15%;
    padding: 1rem;
    display: flex;
    flex-direction: column;
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
