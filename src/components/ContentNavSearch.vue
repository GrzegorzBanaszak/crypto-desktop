<script setup lang="ts">
import SearchIcon from "../icons/SearchIcon.vue";
</script>

<template>
  <div className="main-nav__search">
    <SearchIcon /> <input type="text" placeholder="Search" />
  </div>
</template>

<style lang="scss">
.main {
  &-nav {
    &__search {
      display: flex;
      align-items: center;
      background-color: #f7f7f9;
      border-radius: 8px;
      padding: 0 1.5rem;
      input[type="text"] {
        border: none;
        background-color: #f7f7f9;
        outline: none;
        margin-left: 0.7rem;
        color: #9896a1;
      }
    }
  }
}
</style>
