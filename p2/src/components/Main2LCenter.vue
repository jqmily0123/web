<template>
  <div class="m-con">
    <div class="bg">
      <img src="../assets/5.png" />
    </div>
    <div class="m-center">
      <Title title="今日实时健康诊断概况" class="title"></Title>
      <ul class="datalist">
        <li class="item" v-for="(item, index) in dataList" :key="index">
          <todayData v-bind="item"></todayData>
        </li>
      </ul>
      <div class="chart" id="echarts">
        <!--        <img :src="img" />-->
      </div>
    </div>
  </div>
</template>

<script setup>
import Title from "./Title.vue";
import todayData from "./todayData.vue";
import { ref, onMounted } from "vue";

import * as echarts from "echarts";
const mockList = [];
const getMockData = () => {
  for (let i = 0; i < 5; i++) {
    mockList.push(((Math.random() * 100) / 10 + 5).toFixed(0));
  }
  const sum = mockList.reduce((prev, curr) => {
    return Number(prev) + Number(curr);
  });
  mockList.push(mockList[0]);
  mockList[0] = sum;
  // mockList.push();
};
const getDataList = () => {
  return [
    {
      title: "健康状态",
      subtitle: "A基本概率赋值",
      data: mockList[0],
      stopColor1: "#4BEB8B",
      stopColor2: "#45777C",
      color: "#5A979E",
    },
    {
      title: "亚健康状态",
      subtitle: "B基本概率赋值",
      data: mockList[1],
      stopColor1: "#F4FF5E",
      stopColor2: "#455C69",
      color: "#455C69",
    },
    {
      title: "风险状态",
      subtitle: "C基本概率赋值",
      data: mockList[2],
      stopColor1: "#6e3922",
      stopColor2: "#B7B5A0",
      color: "#B7B5A0",
    },
    {
      title: "故障状态",
      subtitle: "D基本概率赋值",
      data: mockList[3],
      stopColor1: "#e00b0b",
      stopColor2: "#e00b0b",
      color: "#EED5B7",
    },
    {
      title: "安全状态",
      subtitle: "S1基本概率赋值",
      data: mockList[4],
      stopColor1: "#209611",
      stopColor2: "#209611",
      color: "#E5855D",
    },
    {
      title: "不安全状态",
      subtitle: "S2基本概率赋值",
      data: mockList[5],
      stopColor1: "#e359a5",
      stopColor2: "#F7B1A3",
      color: "#F7B1A3",
    },
  ];
};
const dataList = ref({});
getMockData();
dataList.value = getDataList();

const rawData = [];

for (let i = 0; i < 5; i++) {
  const columnData = [];
  let sum = 0;
  for (let j = 0; j < 24; j++) {
    let count = 0;
    if (i === 0) {
      count = columnData.push(Number((Math.random() * 5 + 60).toFixed(2)));
    } else {
      count = columnData.push(Number((Math.random() * 10).toFixed(2)));
    }
    sum += count;
  }
  rawData.push(columnData);
}

const lastData = [];
for (let i = 0; i < 24; i++) {
  let sum = 0;
  for (let j = 0; j < rawData.length; j++) {
    sum += rawData[j][i];
  }
  lastData.push(100 - sum);
}
rawData.push(lastData);
// console.log(rawData);
const grid = {
  left: 0,
  right: 0,
  top: 20,
  bottom: 50,
  containLabel: true,
};
const xAxis = [];
const colors = [
  "#4BEB8B",
  "#F4FF5E",
  "#6E3922",
  "#E359A5",
  "#209611",
  "#E00B0B",
];
for (let i = 1; i < 25; i++) {
  // console.log(i);
  xAxis.push(`${i}:00`);
}
// console.log(xAxis);
const series = [
  "健康状态赋值",
  "亚健康状态赋值",
  "风险状态赋值",
  "故障状态赋值",
  "安全状态赋值",
  "不安全状态赋值",
].map((item, id) => {
  // console.log(id);
  return {
    name: item,
    type: "bar",
    data: rawData[id],
    stack: `total`,
    itemStyle: {
      color: colors[id],
    },
  };
});
// console.log(series);

const option = {
  legend: {
    selectedMode: true,
    bottom: 0,
  },
  grid,
  yAxis: {
    type: "value",
    // showLabel: false,
    // showLabel: false,
    splitLine: false,
    max: 100,
    // interval: 0,
  },
  xAxis: {
    type: "category",
    // showLabel: false,
    data: xAxis,
    // axisLine: {
    //   show: false,
    // },
    axisLabel: {
      // show: false,
      interval: 0,
      fontSize: 10,
    },
    axisTick: {
      show: true,
      alignWithLabel: true,
    },
  },
  series,
};

let chartDom = null;
onMounted(() => {
  chartDom = document.getElementById("echarts");
  // console.log(chartDom);
  const myChart = echarts.init(chartDom);
  option && myChart.setOption(option);
});

// There should not be negative values in rawData
</script>
<style scoped lang="less">
.m-con {
  position: relative;

  .m-center {
    z-index: 2;
    // background-color: red;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .datalist {
      width: 866px;
      height: 125px;
      display: flex;
      justify-content: space-between;
    }
    .chart {
      display: flex;
      width: 870px;
      height: 342px;
      margin-top: 50px;
      z-index: 1000;
      // border: 1px solid red;
    }
    .title {
      z-index: 1000;
      display: flex;
    }
  }
  .bg {
    margin-top: 35px;
    position: absolute;
    top: 0;
    left: 0;
    img {
      z-index: 0;
    }
  }
}
</style>
