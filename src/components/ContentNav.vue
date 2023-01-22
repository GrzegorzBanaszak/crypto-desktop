<script setup lang="ts">
import ContentNavSearch from "./ContentNavSearch.vue";
import ContentNavButton from "./ContentNavButton.vue";
import AlertIcon from "../icons/AlertIcon.vue";
import MenuOpenIcon from "../icons/MenuOpenIcon.vue";
import ContentNavDropdown from "./ContentNavDropdown.vue";
import MenuCloseIcon from "../icons/MenuCloseIcon.vue";
import { ref } from "vue";

const isDropdownOpen = ref<boolean>(false);

const showDropdown = (): void => {
  isDropdownOpen.value = !isDropdownOpen.value;
};
</script>

<template>
  <div className="main-nav">
    <ContentNavSearch />
    <div className="main-nav__btns">
      <ContentNavButton :hasNotif="true"><AlertIcon /></ContentNavButton>
      <ContentNavButton @clickButton="showDropdown">
        <MenuCloseIcon v-if="isDropdownOpen" />
        <MenuOpenIcon v-else />
      </ContentNavButton>
      <ContentNavDropdown v-if="isDropdownOpen" />
    </div>
  </div>
</template>

<style lang="scss">
.main {
  &-nav {
    grid-area: nav;
    display: flex;
    justify-content: space-between;
    padding: 2.2rem 0;
    &__btns {
      display: flex;
      gap: 1rem;
      position: relative;
    }
  }
}
</style>
