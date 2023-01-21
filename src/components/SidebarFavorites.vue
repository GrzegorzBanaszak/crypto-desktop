<script setup lang="ts">
import DotsIcon from "../icons/DotsIcon.vue";
import FavoritesCard from "./FavoritesCard.vue";
</script>

<template>
  <div className="favorites">
    <h4 className="favorites-header">Favorites <DotsIcon /></h4>
    <FavoritesCard
      :diagram-data="[20, 34, 11, 23, 45]"
      :cryptoName="'Bitcoin'"
      :cryptoSymbol="'BTC'"
      :imageName="'Bitcoin.png'"
    />

    <FavoritesCard
      :diagram-data="[24, 15, 17, 23, 17]"
      :cryptoName="'Ripple'"
      :cryptoSymbol="'XRP'"
      :imageName="'CardanoADA.png'"
    />
  </div>
</template>

<style lang="scss">
.favorites {
  border-top: 0.4px solid #9896a1;

  &-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 14px;
    font-weight: 600;
    margin: 0.7rem 0;
    color: #9896a1;
    svg {
      cursor: pointer;
    }
  }
}
</style>
