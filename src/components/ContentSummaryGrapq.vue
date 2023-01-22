<script setup lang="ts">
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
  Filler,
} from "chart.js";

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  scales,
  Filler
);

const chartData = {
  labels: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
  datasets: [
    {
      borderColor: "#7445FB",
      backgroundColor: "rgba(116,69,251,16%)",
      borderWidth: 2,
      data: [
        0, 5000, 10000, 13500, 19000, 25000, 27000, 25000, 18000, 20000, 21432,
      ],
      tension: 0.4,
      pointRadius: 0,

      fill: true,
    },
    {
      borderColor: "#9896A1",
      borderWidth: 2,
      data: [
        0, 7000, 11000, 15000, 16000, 15000, 13000, 10000, 5000, 7000, 9000,
      ],
      tension: 0.4,
      pointRadius: 0,
      showLine: true,
      fill: false,
      borderDash: [4],
    },
  ],
};

const config = {
  responsive: true,
  maintainAspectRatio: false,
  scales: {
    x: {
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

<template><Line :data="chartData" :options="config" /></template>

<style lang="scss"></style>
