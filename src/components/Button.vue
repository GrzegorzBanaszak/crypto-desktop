<script setup lang="ts">
import { PropType } from "vue";
import { ButtonVariant, ButtonType } from "../types/ButtonVariant";

const props = defineProps({
  content: { type: String, required: true },
  variant: { type: Object as PropType<ButtonType> },
});

const buttonType = props.variant?.variant;
</script>

<template>
  <button :className="`button ${buttonType}`">{{ content }}</button>
</template>

<style lang="scss">
.button {
  padding: 1rem 1.3rem;
  font-weight: 600;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  &-blue {
    color: white;
    background-color: #7445fb;
  }
  &-white {
    color: #7445fb;
    background-color: white;
    border: 1px solid #ebebf3;
  }
}
</style>
