<script setup lang="ts">
import Graph from "./Graph.vue";
import Button from "./Button.vue";
import { ButtonVariant } from "../types/ButtonVariant";
import DecreaseIcon from "../icons/DecreaseIcon.vue";
import IncreaseIcon from "../icons/IncreaseIcon.vue";
import { ref } from "vue";

const props = defineProps({
  coinName: { type: String, required: true },
  coinSymbol: { type: String, required: true },
  price: { type: String, required: true },
  change: { type: String, required: true },
});

const imageUrl = new URL(`../assets/${props.coinName}.png`, import.meta.url)
  .href;

const isIncome = ref<boolean>(Number(props.change) > 0 ? true : false);
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
    <div className="tab-card__price">
      <h4>Change</h4>
      <p
        :className="
          isIncome ? 'tab-card__price--income' : 'tab-card__price--decrease'
        "
      >
        {{ change }}% <IncreaseIcon v-if="isIncome" /> <DecreaseIcon v-else />
      </p>
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
  margin: 0.3rem 0;
  padding: 1rem;
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  // display: flex;
  // justify-content: space-between;
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
      color: #9896a1;
      font-weight: 400;
    }
    span {
      font-weight: 600;
      color: #0a041c;
      margin-top: 0.2rem;
    }
  }
  &__price {
    font-size: 14px;

    h4 {
      color: #9896a1;
      font-weight: 400;
    }
    p {
      font-weight: 600;
      display: flex;
      align-items: center;
      margin-top: 0.2rem;
    }
    &--income {
      color: #2dc78f;
    }
    &--decrease {
      color: #ea4d4d;
    }
  }
  &__graph {
    height: 3rem;
    overflow: hidden;
  }
  &__btns {
    display: flex;
    gap: 1rem;
  }
}
</style>
