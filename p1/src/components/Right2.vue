<template>
  <div class="right2">
    <div class="rt">
      <sub-title title="金属构件"></sub-title>
      <div class="rtr">
        <span> 正常使用率 </span>
        <span> 100% </span>
      </div>
    </div>
    <div class="list">
      <Vue3SeamlessScroll :list="data" :hover="true" :wheel="true">
        <div class="row" v-for="item in data" :key="item.id">
          <div class="first">{{ item.name }}</div>
          <div class="center common">
            <div>{{ item.material }}</div>
            <div>材料</div>
          </div>
          <div class="right common">
            <div>{{ item.capacity }}</div>
            <div>主要承力</div>
          </div>
          <div class="footer"></div>
        </div>
      </Vue3SeamlessScroll>
    </div>
  </div>
</template>
<script setup>
import { Vue3SeamlessScroll } from "vue3-seamless-scroll";
import subTitle from "./subTitle.vue";

const data = [
  {
    id: 1,
    name: "起闭杆",
    material: "CCSB",
    capacity: "轴向拉压",
  },
  {
    id: 2,
    name: "背拉杆",
    material: "CCSB",
    capacity: "轴力、剪力、弯矩",
  },
  {
    id: 3,
    name: "面板",
    material: "CCSB",
    capacity: "面内应力、弯曲应力",
  },
  {
    id: 4,
    name: "支枕垫",
    material: "CCSB",
    capacity: "应力、应变",
  },
  {
    id: 5,
    name: "次梁",
    material: "CCSB",
    capacity: "轴力、剪力、弯矩",
  },
  {
    id: 6,
    name: "AB杆",
    material: "CCSB",
    capacity: "轴向拉压",
  },
  {
    id: 7,
    name: "腹板",
    material: "CCSB",
    capacity: "面内应力、弯曲应力",
  },
  {
    id: 8,
    name: "底枢顶盖",
    material: "CCSB",
    capacity: "应力、应变",
  },
];
</script>
<style scoped lang="less">
.right2 {
  height: 302px;
  width: 455px;
  //   background-color: #66FFFF;
  background-color: rgba(18, 41, 83, 0.5);

  .rt {
    padding-top: 5px;
    padding-left: 10px;
    padding-right: 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;

    .rtr {
      display: flex;
      flex-direction: column;
      color: #66ffff;

      span:first-child {
        font-size: 12px;
      }

      span:last-child {
        font-size: 25px;
      }
    }
  }
  .list {
    height: 230px;
    //border: 2px solid #66FFFF;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    //justify-content: space-between;
    //padding: 20px 0;
    //gap: 20px 20px;
    .row {
      height: 86px;
      display: flex;
      //justify-content: ;
      align-items: center;
      //background-color: rgba(102, 255, 255, 0.05);
      border: 1px solid rgba(102, 255, 255, 0.1);
      margin-bottom: 10px;
      position: relative;
      & > div {
        flex: 1;
        display: flex;
        justify-content: center;
      }
      .first {
        color: white;
        font-size: 14px;
      }
      .common {
        display: flex;
        flex-direction: column;
        align-items: center;
        background: url("../assets/rb.svg") no-repeat center -3px;
        position: relative;
        div:last-child {
          color: white;
          font-size: 14px;
          //position: absolute;
          //bottom: 3px;
        }
      }
      .center {
        div:first-child {
          margin-bottom: 10px;
          color: #66ffff;
          font-size: 25px;
        }
      }
      .right {
        div:first-child {
          border-radius: 9px;
          padding: 2px 5px;
          margin-bottom: 22px;
          color: black;
          font-size: 12px;
        }
      }
      &:nth-child(2n) {
        .right div:first-child {
          background-color: #fedb65;
        }
      }
      &:nth-child(2n + 1) {
        .right div:first-child {
          background-color: #66ffff;
        }
      }
      &::before {
        content: "";
        width: 10px;
        height: 10px;
        border-left: 2px solid #66ffff;
        border-top: 2px solid #66ffff;
        position: absolute;
        top: 0;
      }
      &::after {
        content: "";
        width: 10px;
        height: 10px;
        border-right: 2px solid #66ffff;
        border-top: 2px solid #66ffff;
        position: absolute;
        top: 0;
        right: 0;
      }
      & .footer {
        position: absolute;
        width: 100%;
        height: 100%;
        //background-color: #66FFFF;
        &::before {
          content: "";
          width: 10px;
          height: 10px;
          border-left: 2px solid #66ffff;
          border-bottom: 2px solid #66ffff;
          position: absolute;
          bottom: 0;
          left: 0;
        }
        &::after {
          content: "";
          width: 10px;
          height: 10px;
          border-right: 2px solid #66ffff;
          border-bottom: 2px solid #66ffff;
          position: absolute;
          bottom: 0;
          right: 0;
        }
      }
    }
  }
}
</style>
