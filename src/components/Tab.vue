<script setup lang="ts">
const props = defineProps({
  text: { type: String, required: true },
  isSelect: { type: Boolean },
});

const emit = defineEmits(["tabClick"]);

const tabClick = (): void => {
  emit("tabClick");
};
</script>

<template>
  <div @click="tabClick" :className="`tab ${isSelect && 'tab--active'}`">
    {{ text }}
    <div v-if="isSelect" className="tab--underline"></div>
  </div>
</template>

<style lang="scss">
.tab {
  padding: 1rem 0;
  position: relative;
  color: #9896a1;
  cursor: pointer;
  &--active {
    color: #0a041c;
    font-weight: 600;
  }
  &--underline {
    position: absolute;
    right: 0;
    bottom: 0;
    width: 100%;
    height: 4px;
    background-color: #7445fb;
  }
}
</style>
