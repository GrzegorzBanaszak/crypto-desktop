<script setup lang="ts">
import { ref } from "vue";
import TabCard from "./TabCard.vue";
import axios from "axios";

const { data } = await axios.get("/api/v1/cryptocurrency/listings/latest", {
  params: { limit: 3 },
  headers: {
    "X-CMC_PRO_API_KEY": import.meta.env.VITE_ACCESS_TOKEN,
    "Content-Type": "application/json;charset=UTF-8",
    "Access-Control-Allow-Origin": "*",
  },
  withCredentials: false,
});
</script>

<template>
  <TabCard
    v-for="item in data.data"
    :key="item.id"
    :change="item.quote.USD.percent_change_24h.toFixed(2)"
    :coin-name="item.name"
    :coin-symbol="item.symbol"
    :price="item.quote.USD.price.toFixed(2)"
  />
</template>

<style lang="scss"></style>
