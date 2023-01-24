<script setup lang="ts">
import Tab from "./Tab.vue";
import { ref } from "vue";
import TabsSummary from "./TabsSummary.vue";

const selected = ref<string>("Summary");
const changeSelected = (select: string): void => {
  selected.value = select;
};
</script>

<template>
  <div className="main-tabs">
    <div className="main-tabs__header">
      <Tab
        text="Summary"
        :isSelect="selected === 'Summary'"
        @tabClick="changeSelected('Summary')"
      />
      <Tab
        text="Table"
        :isSelect="selected === 'Table'"
        @tabClick="changeSelected('Table')"
      />
      <Tab
        text="Charts"
        :isSelect="selected === 'Charts'"
        @tabClick="changeSelected('Charts')"
      />
      <Tab
        text="Reporting"
        :isSelect="selected === 'Reporting'"
        @tabClick="changeSelected('Reporting')"
      />
      <Tab
        text="Analysis"
        :isSelect="selected === 'Analysis'"
        @tabClick="changeSelected('Analysis')"
      />
    </div>
    <div className="main-tabs__body">
      <Suspense v-if="selected === 'Summary'">
        <TabsSummary />
        <template #fallback> Loading... </template>
      </Suspense>
      <div v-else-if="selected === 'Table'">Table</div>
      <div v-else-if="selected === 'Charts'">Charts</div>
      <div v-else-if="selected === 'Reporting'">Reporting</div>
      <div v-else-if="selected === 'Analysis'">Analysis</div>
      <div v-else>Error</div>
    </div>
  </div>
</template>

<style lang="scss">
.main {
  &-tabs {
    grid-area: tabs;
    background-color: #f7f7f9;
    border-radius: 16px;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    &__header {
      display: flex;
      gap: 1rem;
      border-bottom: 1px solid #ebebf3;
    }
    &__body {
      padding-top: 1rem;
    }
  }
}
</style>
