<script setup lang="ts">
import DotsIcon from "../icons/DotsIcon.vue";

const props = defineProps({
  fullName: { type: String, required: true },
  email: { type: String, required: true },
  imageName: { type: String, required: true },
});

const imageUrl = new URL(`../assets/${props.imageName}`, import.meta.url).href;
</script>

<template>
  <div className="user-card">
    <div className="user-card__image">
      <img className="user-card__image" :src="imageUrl" alt="User card image" />
    </div>
    <div className="user-card__info">
      <h4>Marc Webber</h4>
      <span>marc@riot.com</span>
    </div>
    <div className="user-card__dottes">
      <DotsIcon />
    </div>
  </div>
</template>

<style lang="scss">
.user-card {
  display: flex;
  margin-top: auto;
  align-items: center;
  &__image {
    img {
      border-radius: 50%;
    }
  }
  &__info {
    margin-left: 0.6rem;
    font-size: 14px;
    h4 {
      font-weight: 600;
      color: #0a041c;
    }
    span {
      color: #9896a1;
    }
  }
  &__dottes {
    margin-left: auto;
    margin-right: 0;
    cursor: pointer;
  }
}
</style>
