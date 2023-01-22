<script setup lang="ts">
import DotsIcon from "../icons/DotsIcon.vue";
import IncomeIcon from "../icons/IncomeIcon.vue";
import { ButtonVariant } from "../types/ButtonVariant";
import Button from "./Button.vue";
</script>

<template>
  <div className="main-balance">
    <h2 className="main-balance__header">Current Balance <DotsIcon /></h2>
    <div className="main-balance__founds"><span>$</span>21 432.23</div>
    <p className="main-balance__income"><IncomeIcon /> 12% vs last month</p>
    <div className="main-balance__btns">
      <Button
        content="Quick Invest"
        :variant="{ variant: ButtonVariant.blue }"
      />
      <Button
        content="Show Report"
        :variant="{ variant: ButtonVariant.white }"
      />
    </div>
  </div>
</template>

<style lang="scss">
.main {
  &-balance {
    grid-area: balance;
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
    &__founds {
      margin-top: 2rem;
      font-size: 3.5rem;
      color: #0a041c;
      font-weight: 600;
      span {
        color: #9896a1;
        font-weight: 400;
      }
    }
    &__income {
      margin-top: 0.3rem;
      display: flex;
      color: #2dc78f;
      font-weight: 600;
      font-size: 1.125rem;
    }
    &__btns {
      margin-top: auto;
      display: flex;
      gap: 1rem;
    }
  }
}
</style>
