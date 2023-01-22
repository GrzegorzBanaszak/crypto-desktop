<script setup lang="ts">
const props = defineProps({
  /**
   * Display notification for button
   */
  hasNotif: Boolean,
});

const emit = defineEmits(["clickButton"]);

const clickButton = (): void => {
  emit("clickButton");
};
</script>

<template>
  <button @click="clickButton" className="main-nav__button">
    <slot></slot>
    <span v-if="hasNotif" className="main-nav__button--notif"></span>
  </button>
</template>

<style lang="scss">
.main {
  &-nav {
    &__button {
      background-color: #f7f7f9;
      width: 48px;
      height: 48px;
      border: none;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 8px;
      cursor: pointer;
      position: relative;
      &--notif {
        position: absolute;
        top: 0;
        right: 0;
        background-color: #ea4d4d;
        width: 12px;
        height: 12px;
        border-radius: 50%;
      }
    }
  }
}
</style>
