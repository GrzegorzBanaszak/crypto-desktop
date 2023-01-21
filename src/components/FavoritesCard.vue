<script setup lang="ts">
import Graph from "./Graph.vue";

const props = defineProps({
  cryptoName: { type: String, required: true },
  cryptoSymbol: { type: String, required: true },
  diagramData: { type: Array<number>, required: true },
  imageName: { type: String, required: true },
});

const imageUrl = new URL(`../assets/${props.imageName}`, import.meta.url).href;

const isGrown = (): string => {
  const lenght = props.diagramData?.length;
  if (props.diagramData[lenght - 1] > props.diagramData[lenght - 2])
    return "green";
  else return "red";
};
</script>

<template>
  <div className="fav-card">
    <div className="fav-card__icon">
      <img alt="Crypto image" v-bind:src="imageUrl" />
    </div>
    <div className="fav-card__name">
      <span>{{ cryptoSymbol }}</span>
      <h4>{{ cryptoName }}</h4>
    </div>
    <div className="fav-card__diagram">
      <Graph :color="isGrown()" :diagramData="diagramData" />
    </div>
  </div>
</template>

<style lang="scss">
.fav-card {
  display: flex;
  margin: 1rem 0;
  &__icon {
    width: 2rem;
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    img {
      width: 70%;
    }
  }
  &__name {
    margin-left: 0.6rem;
    font-size: 12px;
    h4 {
      font-weight: 600;
      color: #0a041c;
    }
    span {
      color: #9896a1;
    }
  }
  &__diagram {
    height: 2rem;
    margin-left: auto;
  }
}
</style>
