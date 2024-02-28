<template>
  <div class="container mx-[300px]">
    <div class="grid grid-cols-2 gap-10">
      <div class="bg-[#f5f3f3] shadow-md w-[500px] h-[400px] rounded-md">
        <ClientOnly>
          <VueApexCharts
            type="line"
            :options="myLineChart"
            :series="myLineChart.series"
            class="w-[500px] mt-10"
          />
        </ClientOnly>
      </div>
      <div class="bg-[#f5f3f3] shadow-md w-[500px] h-[400px] rounded-md">
        <ClientOnly>
          <VueApexCharts
            type="line"
            :options="mySecondChart"
            :series="mySecondChart.series"
            class="w-[500px] mt-10"
          />
        </ClientOnly>
      </div>
      <div class="bg-[#f5f3f3] shadow-md w-[500px] h-[400px] rounded-md">
        <ClientOnly>
          <VueApexCharts
            type="radar"
            :options="myRadarChart"
            :series="myRadarChart.series"
            class="w-full mt-10"
          />
        </ClientOnly>
      </div>
      <div class="bg-[#f5f3f3] shadow-md w-[500px] h-[400px] rounded-md">
        <ClientOnly>
          <VueApexCharts
            type="pie"
            :options="myPieChart"
            :series="myPieChart.series"
            class="w-[500px] mt-10"
          />
        </ClientOnly>
      </div>
    </div>
  </div>
</template>

<script setup>
import VueApexCharts from "vue3-apexcharts";
// one charts
const myLineChart = ref({
  series: [
    {
      name: "Mamusha",
      data: [13, 67, 43, 32, 77, 87],
    },
  ],
  chart: {
    height: 300,
    type: "line",
    zoom: {
      enabled: true,
    },
  },
  dataLabels: {
    enabled: false,
  },
  stroke: {
    curve: "straight",
  },
  title: {
    text: "Mam charts",
    align: "left",
  },
  grid: {
    row: {
      colors: ["#dff"],
      opacity: 0.5,
    },
  },
  xaxis: {
    catagories: ["jan", "feb", "mar", "apr", "may", "jun"],
  },
});

//two charts

const mySecondChart = ref({
  series: [
    {
      name: "Mamush chart 2",
      data: [1, 23, 43, 15, 28, 50],
    },
    {
      name: "Mamush chart dowbled chart 2",
      data: [33, 3, 43, 10, 50, 25],
    },
  ],
  chart: {
    height: 350,
    type: "line",
    dropShadow: {
      enabled: true,
      color: "#dcb",
      top: 18,
      left: 7,
      blur: 10,
      opacity: 0.2,
    },
    toolbar: {
      show: false,
    },
  },
  colors: ["#d9f", "#f5b", "#feb", "#f1d", "#dfb"],
  dataLabels: {
    enabled: true,
  },
  stroke: {
    curve: "smooth",
  },
  title: {
    text: "Temprature",
    align: "left",
  },
  grid: {
    borderColor: "green",
    row: {
      colors: ["#eff"],
      opacity: 0.5,
    },
  },
  markers: {
    size: 1,
  },
  xaxis: {
    catagories: ["jan", "feb", "mar", "apr", "may", "jun"],
    title: {
      text: "Temprature",
    },
  },
  yaxis: {
    title: {
      text: "Temprature 2",
    },
    min: 5,
    max: 50,
  },
  legend: {
    position: "top",
    horizontalAlignment: "right",
    floating: true,
    offsetY: -25,
    offsetX: -5,
  },
});

const myRadarChart = ref({
  series: [
    {
      name: " readar chart 1",
      data: [80, 32, 44, 97, 21, 66, 77],
    },
    {
      name: " readar chart 2",
      data: [40, 72, 55, 27, 81, 6, 77],
    },
    {
      name: " readar chart 3",
      data: [10, 82, 44, 97, 1, 86, 37],
    },
  ],
  chart: {
    type: "radar",
    height: 350,
    dropShadow: {
      enabled: true,
      blur: 1,
      left: 1,
      top: 1,
    },
  },
  title: {
    text: "Readar chart practice",
  },
  stroke: {
    width: 2,
  },
  fill: {
    opacity: 0.1,
  },
  markers: {
    size: 0,
  },
  xaxis: {
    catagories: ["2011", "2012", "2013", "2014", "2015", "2016"],
  },
});

const myPieChart = ref({
  series: [44, 56, 22, 90, 32, 88],
  chart: {
    type: "pie",
    width: 480,
  },
  labels: ["Mamush", "Bete", "Abe", "Alex", "belay", "ermi"],
  responsive: [
    {
      breakpoint: 480,
      options: {
        chart: {
          width: 200,
        },
      },
    },
  ],
  legend: {
    position: "bottom",
  },
});
</script>

<style></style>
