<script setup lang="ts"></script>

<template>
  <div className="main-nav__dropdown">
    <ul>
      <li>About us</li>
      <li>Contact</li>
    </ul>
  </div>
</template>

<style lang="scss">
.main {
  &-nav {
    &__dropdown {
      position: absolute;
      top: 50px;
      width: 150px;
      box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
      padding: 1rem 2rem;
      right: 0;
      background-color: white;
      ul {
        list-style-type: none;
      }
      li {
        margin: 1rem 0;
        font-size: 16px;
      }
    }
  }
}
</style>
