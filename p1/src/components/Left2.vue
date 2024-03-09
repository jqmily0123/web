<template>
  <div class="left2">
    <subTitle title="工作闸门计算结果"></subTitle>
    <div class="main">
      <Vue3SeamlessScroll
        v-if="data"
        :list="data"
        class="list"
        :hover="true"
        :wheel="true"
      >
        <div class="row" v-for="item in data" :key="item.id">
          <span>{{ item.name }}</span>
          <span>{{ item.result }}</span>
          <span>{{ item.permissions }}</span>
          <span>{{ item.workStation }}</span>
        </div>
      </Vue3SeamlessScroll>
    </div>
  </div>
</template>
<script setup>
import subTitle from "./subTitle.vue";
import { Vue3SeamlessScroll } from "vue3-seamless-scroll";

const data = [
  {
    id: "1",
    name: "人字门最大径向位移Uy",
    result: "计算结果：7.04mm",
    permissions: "",
    workStation: "无水悬挂工况",
  },
  {
    id: "2",
    name: "人字门最大竖向位移Uz",
    result: "计算结果：2.81mm",
    permissions: "",
    workStation: "无水悬挂工况",
  },
  {
    id: "3",
    name: "人字门门轴柱端最大径向位移Uy",
    result: "计算结果：0.44mm",
    permissions: "",
    workStation: "无水悬挂工况",
  },
  {
    id: "4",
    name: "人字门斜接柱端最大径向位移Uy",
    result: "计算结果：7.07mm",
    permissions: "",
    workStation: "无水悬挂工况",
  },
  {
    id: "5",
    name: "人字门斜接柱门轴柱最大相对径向位移",
    result: "计算结果：2.00mm",
    permissions: "",
    workStation: "无水悬挂工况",
  },
  {
    id: "6",
    name: "人字门斜接柱门轴柱最大相对竖向位移",
    result: "计算结果：4.39mm",
    permissions: "允许值：5mm",
    workStation: "无水悬挂工况",
  },

  {
    id: "7",
    name: "人字门主梁腹板最大梁向拉应力σ",
    result: "计算结果：24.27MPa",
    permissions: "允许值：144MPa",
    workStation: "无水悬挂工况",
  },
  {
    id: "8",
    name: "人字门主梁腹板最大梁向压应力σ",
    result: "计算结果：26.67MPa",
    permissions: "允许值：144MPa",
    workStation: "无水悬挂工况",
  },
  {
    id: "9",
    name: "人字门最大折算应力σzh",
    result: "计算结果：26.91MPa",
    permissions: "允许值：158MPa",
    workStation: "无水悬挂工况",
  },
  {
    id: "10",
    name: "人字门顶枢最大折算应力σzh",
    result: "计算结果：24.96MPa",
    permissions: "允许值：158MPa",
    workStation: "无水悬挂工况",
  },
  {
    id: "11",
    name: "人字门底枢最大折算应力σzh",
    result: "计算结果：26.67MPa",
    permissions: "允许值：158MPa",
    workStation: "无水悬挂工况",
  },
  {
    id: "12",
    name: "人字门主梁腹板剪应力τxy",
    result: "计算结果：13.42MPa",
    permissions: "允许值：85.5MPa",
    workStation: "无水悬挂工况",
  },
  {
    id: "13",
    name: "人字门最大径向位移Uy",
    result: "计算结果：12.89mm",
    permissions: "",
    workStation: "开门运行工况",
  },
  {
    id: "14",
    name: "人字门最大竖向位移Uz",
    result: "计算结果：0.22mm",
    permissions: "",
    workStation: "开门运行工况",
  },
  {
    id: "15",
    name: "人字门门轴柱端最大径向位移Uy",
    result: "计算结果：0.41mm",
    permissions: "",
    workStation: "开门运行工况",
  },
  {
    id: "16",
    name: "人字门斜接柱端最大径向位移Uy",
    result: "计算结果：12.67mm",
    permissions: "",
    workStation: "开门运行工况",
  },
  {
    id: "17",
    name: "人字门斜接柱门轴柱最大相对径向位移",
    result: "计算结果：12.91mm",
    permissions: "",
    workStation: "开门运行工况",
  },
  {
    id: "18",
    name: "人字门斜接柱门轴柱最大相对竖向位移",
    result: "计算结果：0.80mm",
    permissions: "",
    workStation: "开门运行工况",
  },

  {
    id: "19",
    name: "人字门主梁腹板最大梁向拉应力σ",
    result: "计算结果：31.46MPa",
    permissions: "允许值：144MPa",
    workStation: "开门运行工况",
  },
  {
    id: "20",
    name: "人字门主梁腹板最大梁向拉应力σ",
    result: "计算结果：25.67MPa",
    permissions: "允许值：144MPa",
    workStation: "开门运行工况",
  },
  {
    id: "21",
    name: "人字门最大折算应力σzh",
    result: "计算结果：44.77MPa",
    permissions: "允许值：158MPa",
    workStation: "开门运行工况",
  },
  {
    id: "22",
    name: "人字门主梁腹板剪应力τxy",
    result: "计算结果：15.77MPa",
    permissions: "允许值：85.5MPa",
    workStation: "开门运行工况",
  },
  {
    id: "23",
    name: "人字门最大径向位移Uy",
    result: "计算结果：22.27mm",
    permissions: "",
    workStation: "关门运行工况",
  },
  {
    id: "24",
    name: "人字门最大竖向位移Uz",
    result: "计算结果：3.77mm",
    permissions: "",
    workStation: "关门运行工况",
  },
  {
    id: "25",
    name: "人字门门轴柱端最大径向位移Uy",
    result: "计算结果：0.78mm",
    permissions: "",
    workStation: "关门运行工况",
  },
  {
    id: "26",
    name: "人字门斜接柱端最大径向位移Uy",
    result: "计算结果：21.85mm",
    permissions: "",
    workStation: "关门运行工况",
  },
  {
    id: "27",
    name: "人字门斜接柱门轴柱最大相对径向位移",
    result: "计算结果：22.31mm",
    permissions: "",
    workStation: "关门运行工况",
  },
  {
    id: "28",
    name: "人字门斜接柱门轴柱最大相对竖向位移",
    result: "计算结果：3.30mm",
    permissions: "",
    workStation: "关门运行工况",
  },

  {
    id: "29",
    name: "人字门主梁腹板最大梁向压应力σ",
    result: "计算结果：43.69MPa",
    permissions: "允许值：144MPa",
    workStation: "关门运行工况",
  },
  {
    id: "30",
    name: "人字门主梁腹板最大梁向拉应力σ",
    result: "计算结果：28.49MPa",
    permissions: "允许值：144MPa",
    workStation: "关门运行工况",
  },
  {
    id: "31",
    name: "人字门最大折算应力σzh",
    result: "计算结果：56.12MPa",
    permissions: "允许值：158MPa",
    workStation: "关门运行工况",
  },
  {
    id: "32",
    name: "人字门主梁腹板剪应力τxy",
    result: "计算结果：85.5MPa",
    permissions: "允许值：85.5MPa",
    workStation: "关门运行工况",
  },
  {
    id: "33",
    name: "人字门最大径向位移Uy",
    result: "计算结果：3.65mm",
    permissions: "",
    workStation: "关门挡水工况",
  },
  {
    id: "34",
    name: "人字门最大竖向位移Uz",
    result: "计算结果：1.92mm",
    permissions: "",
    workStation: "关门挡水工况",
  },
  {
    id: "35",
    name: "人字门门轴柱端最大径向位移Uy",
    result: "计算结果：0.10mm",
    permissions: "",
    workStation: "关门挡水工况",
  },
  {
    id: "36",
    name: "人字门斜接柱端最大径向位移Uy",
    result: "计算结果：1.93mm",
    permissions: "",
    workStation: "关门挡水工况",
  },
  {
    id: "37",
    name: "人字门斜接柱门轴柱最大相对径向位移",
    result: "计算结果：1.74mm",
    permissions: "",
    workStation: "关门挡水工况",
  },
  {
    id: "38",
    name: "人字门斜接柱门轴柱最大相对竖向位移",
    result: "计算结果：0.51mm",
    workStation: "关门挡水工况",
    permissions: "",
  },

  {
    id: "39",
    name: "人字门主梁腹板最大梁向压应力σ",
    result: "计算结果：51.74MPa",
    permissions: "允许值：144MPa",
    workStation: "关门挡水工况",
  },
  {
    id: "40",
    name: "人字门主梁腹板最大梁向拉应力σ",
    result: "计算结果：10.36MPa",
    permissions: "允许值：144MPa",
    workStation: "关门挡水工况",
  },
  {
    id: "41",
    name: "人字门最大折算应力σzh",
    result: "计算结果：54.82MPa",
    permissions: "允许值：158MPa",
    workStation: "关门挡水工况",
  },
  {
    id: "42",
    name: "人字门主梁腹板剪应力τxy",
    result: "计算结果：22.27MPa",
    permissions: "允许值：85.5MPa",
    workStation: "关门挡水工况",
  },
];
</script>
<style scoped lang="less">
.left2 {
  width: 465px;
  height: 372px;

  .main {
    width: 100%;
    height: 300px;
    color: white;
    font-size: 12px;
    overflow: hidden;

    .list {
      .row {
        width: 100%;
        height: 50px;
        //text-align: center;
        //line-height: 50px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        span {
          opacity: 1;
          height: 50px;
          word-break: break-all;
          display: flex;
          align-items: center;
          text-align: center;
        }
        span:nth-child(1) {
          width: 95px;
        }
        span:nth-child(2) {
          width: 122px;
        }
        span:nth-child(3) {
          width: 100px;
        }
        span:nth-child(4) {
          width: 74px;
        }
      }
      div:nth-child(2n) {
        background-color: rgba(3, 157, 206, 0.1);
      }
    }
    .list {
      div:nth-child(2n + 1) {
        background-color: rgba(3, 157, 206, 0.2);
      }
    }
  }
}
</style>
