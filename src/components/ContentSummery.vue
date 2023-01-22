<script setup lang="ts">
import DotsIcon from "../icons/DotsIcon.vue";
import ContentSummeryGrapq from "./ContentSummaryGrapq.vue";
</script>

<template>
  <div className="main-summary">
    <h2 className="main-summary__header">Summary<DotsIcon /></h2>
    <div className="main-summary__grapq">
      <ContentSummeryGrapq />
    </div>
    <div className="main-summary__info">
      <div className="main-summary__info--this"><span></span> This month</div>
      <div className="main-summary__info--last"><span></span> Last month</div>
    </div>
  </div>
</template>

<style lang="scss">
.main {
  &-summary {
    grid-area: summary;
    background-color: #f7f7f9;
    border-radius: 16px;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    &__header {
      display: flex;
      align-items: center;
      font-weight: 600;
      font-size: 22px;
      justify-content: space-between;
      svg {
        cursor: pointer;
      }
    }
    &__grapq {
      margin-top: 1rem;
      height: 250px;
      position: relative;
    }
    &__info {
      margin-top: 0.3rem;
      border-top: 1px solid #d5d5d6;
      padding-top: 1.3rem;
      display: flex;
      color: #9896a1;
      gap: 1rem;
      span {
        width: 0.5rem;
        height: 0.5rem;
        border-radius: 50%;
        display: inline-block;
        margin-right: 0.4rem;
      }
      &--this {
        span {
          background-color: #7445fb;
        }
      }
      &--last {
        span {
          background-color: #d5d5d6;
        }
      }
    }
  }
}
</style>
