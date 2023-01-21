<script setup lang="ts">
import { ref } from "vue";
import { Line } from "vue-chartjs";
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  scales,
} from "chart.js";

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  scales
);

const props = defineProps({
  color: { type: String, required: true },
  diagramData: { type: Array<number>, required: true },
});

const chartData = {
  labels: props.diagramData,

  datasets: [
    {
      borderColor: props.color,
      borderWidth: 2,
      data: props.diagramData,
      tension: 0.4,
      pointRadius: 0,
    },
  ],
};

const config = {
  scales: {
    x: {
      display: false,
    },
    y: {
      display: false,
    },
  },
  plugins: {
    legend: {
      display: false,
    },
  },
};
</script>

<template>
  <Line :data="chartData" :options="config" />
</template>

<style></style>
