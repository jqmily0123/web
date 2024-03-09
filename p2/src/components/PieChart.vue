<template>
  <div class="container">
    <div id="pie"></div>
    <div class="title">
      <div class="text1">健康</div>
      <div class="text2">综合评估</div>
    </div>
    <div class="legend">
      <div class="item" v-for="item in legendData" :key="item.id">
        <div class="left" :style="{ backgroundColor: item.iconColor }"></div>
        <div class="right">
          <div class="r_top">{{ item.text }}</div>
          <div class="r_bottom">{{ item.data }}<span>%</span></div>
        </div>
      </div>
    </div>
    <div class="svg">
      <img src="../assets/outer.svg" />
      <img src="../assets/inner.svg" />
    </div>
  </div>
</template>

<script setup>
import * as echarts from "echarts";
import { onMounted } from "vue";
const option = {
  title: {
    // text: "123",
  },
  tooltip: {
    trigger: "item",
  },

  series: [
    {
      name: "Access From",

      type: "pie",
      radius: ["40%", "70%"],
      avoidLabelOverlap: false,
      itemStyle: {
        borderRadius: 10,
        // borderColor: "#fff",
        borderWidth: 5,
      },
      label: {
        show: false,
        position: "center",
      },
      labelLine: {
        show: true,
      },
      data: [
        { value: 1048, name: "Search Engine" },
        { value: 735, name: "Direct" },
        { value: 580, name: "Email" },
        { value: 484, name: "Union Ads" },
        { value: 300, name: "Video Ads" },
      ],
    },
  ],
};

onMounted(() => {
  const chartDom = document.getElementById("pie");
  const myChart = echarts.init(chartDom);
  option && myChart.setOption(option);
});
// console.log(123);
const colors = [
  "#4BEB8B",
  "#F4FF5E",
  "#6E3922",
  "#E359A5",
  "#209611",
  "#E00B0B",
];
const legendData = [
  {
    id: 0,
    iconColor: colors[0],
    text: "健康状态概率赋值",
    data: "99.993",
  },
  {
    id: 1,
    iconColor: colors[1],
    text: "亚健康状态概率赋值",
    data: "0.006",
  },
  {
    id: 2,
    iconColor: colors[2],
    text: "风险状态概率赋值",
    data: "0.000",
  },
  {
    id: 3,
    iconColor: colors[3],
    text: "故障状态概率赋值",
    data: "0.000",
  },
  {
    id: 4,
    iconColor: colors[4],
    text: "安全状态概率赋值",
    data: "0.001",
  },
  {
    id: 5,
    iconColor: colors[5],
    text: "不安全状态概率赋值",
    data: "1.569",
  },
];
</script>
<style scoped lang="less">
.container {
  //position: absolute;
  width: 300px;
  height: 520px;
  position: relative;
  //display: flex;
  //align-items: center;
  #pie {
    width: 100%;
    height: 300px;
    //border: 1px solid red;
  }
  //border: 1px solid red;
  //z-index: 10000;
  .title {
    color: white;
    position: absolute;
    bottom: 0;
    //z-index: 10000;
    //position: absolute;
    left: 50%;
    transform: translateX(-50%);
    //position: absolute;
    top: 130px;
    .text1 {
      font-size: 20px;
      font-weight: bold;
      text-align: center;
    }
    .text1 {
      font-size: 16px;
      font-weight: bold;
    }
  }
  .legend {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    //border: 2px green solid;
    margin-top: 30px;
    .item {
      width: 150px;
      height: 36px;
      display: flex;
      //justify-content: center;
      align-items: center;
      margin-bottom: 30px;

      .left {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        margin-right: 10px;
      }
      .right {
        .r_top {
          font-size: 13px;
          color: #f0f0f0;
        }
        .r_bottom {
          color: #fff;
          font-size: 20px;
          span {
            font-size: 14px;
          }
        }
      }
    }
  }
  .svg {
    top: 30px;
    img {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      //position: absolute;
      top: 30px;
    }
  }
}
</style>
