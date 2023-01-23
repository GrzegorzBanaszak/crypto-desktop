<script setup lang="ts">
import Graph from "./Graph.vue";
import Button from "./Button.vue";
import { ButtonVariant } from "../types/ButtonVariant";
const props = defineProps({
  coinName: { type: String, required: true },
  coinSymbol: { type: String, required: true },
  price: { type: Number, required: true },
  change: { type: Number, required: true },
});

const imageUrl = new URL(`../assets/${props.coinName}.png`, import.meta.url)
  .href;
</script>

<template>
  <div className="tab-card">
    <div className="tab-card__icon">
      <img :src="imageUrl" alt="User card image" />
    </div>
    <div className="tab-card__info">
      <h4>{{ coinSymbol }}</h4>
      <span>{{ coinName }}</span>
    </div>
    <div className="tab-card__info">
      <h4>Price</h4>
      <span>${{ price }}</span>
    </div>
    <div className="tab-card__info">
      <h4>Change</h4>
      <span>{{ change }}</span>
    </div>
    <div className="tab-card__graph">
      <Graph :color="'green'" :diagramData="[3, 3, 1, 4, 5]" />
    </div>
    <div className="tab-card__btns">
      <Button
        :content="'Sell'"
        :variant="{ variant: ButtonVariant.white }"
      ></Button>
      <Button
        :content="'Buy'"
        :variant="{ variant: ButtonVariant.blue }"
      ></Button>
    </div>
  </div>
</template>

<style lang="scss">
.tab-card {
  background-color: white;
  border: 1px solid #ebebf3;
  border-radius: 8px;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  &__icon {
    width: 3rem;
    height: 3rem;
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    img {
      width: 70%;
    }
  }
  &__info {
    font-size: 14px;
    h4 {
      font-weight: 600;
      color: #0a041c;
    }
    span {
      color: #9896a1;
    }
  }
  &__price {
    font-size: 14px;
    h4 {
      color: #9896a1;
    }
    span {
      font-weight: 600;
      color: #0a041c;
    }
  }
  &__graph {
    height: 3rem;
  }
  &__btns {
    display: flex;
    gap: 1rem;
  }
}
</style>
