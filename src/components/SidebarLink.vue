<template>
  <router-link className="link" :to="linkTarget"
    ><slot></slot> {{ linkText }}
    <span v-if="notification" className="link-notification"
      >+{{ notification }}</span
    >
  </router-link>
</template>

<script setup lang="ts">
const props = defineProps({
  linkTarget: { type: String, required: true },
  linkText: { type: String, required: true },
  notification: { type: Number },
});
</script>

<style lang="scss">
.link {
  stroke: #9896a1;
  color: #9896a1;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem;
  border-radius: 4px;
  margin: 1.2rem 0;
  &:hover {
    background-color: white;
    cursor: pointer;
    stroke: #7445fb;
    color: #0a041c;
    font-weight: 600;
  }
  &-notification {
    background-color: #ea4d4d;
    color: white;
    border-radius: 30px;
    font-size: 10px;
    padding: 0.2rem 0.5rem;
    margin-left: auto;
    font-weight: 700;
  }
}
</style>
