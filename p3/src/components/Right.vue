<template>
  <div class="right">
    <bgBox v-bind="right1"  class="box1">
    </bgBox>
    <bgBox v-bind="right2" class="box2">
    </bgBox>
  </div>
</template>

<script setup>
import bgBox from "./bgBox.vue";
const right1 = {
  title: "传感器参数",
  width: "440px",
  height: "502px",
  bgurl: "../../public/bg1.svg",
  whichbg: "1",
  subtitle: "三向加速度传感器",
  list: [
    {
      name: "型号",
      dec: "1A731E压电式加速度传感器（三向）",
    },
    {
      name: "用途",
      dec: "水下振动监测",
    },
    {
      name: "灵敏度",
      dec: "18 ~ 28℃    X、Y、Z向~100mV/g",
    },
    {
      name: "量程",
      dec: "- 50 ~ 50 g",
    },
    {
      name: "频率响应",
      dec: "-10 ~ 10%      0.5~10000Hz",
    },
    {
      name: "分辨率",
      dec: "0.0002 g",
    },
    {
      name: "冲击极限",
      dec: "无供电           2000g",
    },
  ],
};
const right2 = {
  title: "传感器布置方案",
  width: "440px",
  height: "331px",
  bgurl: "../../public/bg2.svg",
  whichbg: "2",
  list: [
    {
      name: "C210-78",
      dec: "1#主梁斜接柱侧边隔板",
      dec2: "防水型应变计",
    },
    {
      name: "DX011",
      dec: "10#主梁腹板跨中(靠下游)",
      dec2: "单向加速度计",
    },
    {
      name: "SX007",
      dec: "1#主梁腹板斜接柱侧加强段",
      dec2: "三向加速度计",
    },
    {
      name: "QJ003",
      dec: "10#主梁腹板斜接柱侧加强段",
      dec2: "倾角应变计",
    },
    {
      name: "YB002",
      dec: "1#主梁斜接柱侧边隔板",
      dec2: "应变传感器",
    },
    {
      name: "YB018",
      dec: "主背拉杆(近斜接柱侧下杆)",
      dec2: "应变传感器",
    },
  ],
};
</script>
<style scoped lang="less">
.right {
  width: 440px;
  .box2 {
    margin-top: 40px;
  }

  img {
    width: calc(100% - 2px);
    // height: 100%;
    top: 40px;
    position: absolute;
  }
}
</style>
