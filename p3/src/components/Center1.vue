<template>
  <div class="center1">
    <center-header></center-header>
    <div class="center-img">
      <img src="../assets/center2.png" alt="" class="sebei" />
      <component
        :is="data.components[currentIndex].comName"
        class="single"
      ></component>
      <div class="btns">
        <button @click="handle(0)"></button>
        <button @click="handle(1)"></button>
        <button @click="handle(2)"></button>
        <button @click="handle(3)"></button>
      </div>
    </div>
  </div>
</template>

<script setup>
import centerHeader from "./centerHeader.vue";
// import circleBox from "./circleBox.vue";
// import single from "./single.vue";
import singleBox from "./singleBox.vue";
import threePhases from "./threePhases.vue";
import underWater from "./underWater.vue";
import inclinationBox from "./inclinationBox.vue";
import { reactive, markRaw, ref } from "vue";
const data = reactive({
  components: [
    {
      name: "underWater",
      comName: markRaw(underWater),
    },
    {
      name: "threePhases",
      comName: markRaw(threePhases),
    },
    {
      name: "singleBox",
      comName: markRaw(singleBox),
    },
    {
      name: "inclinationBox",
      comName: markRaw(inclinationBox),
    },
  ],
});

const currentIndex = ref(0);
const handle = (index) => {
  currentIndex.value = index;
};
</script>
<style scoped lang="less">
.center1 {
  // background-color: red;

  width: 900px;
  position: relative;
  .center-img {
    // border: 1px solid red;
    height: 768px;
    text-align: center;
    position: relative;
    background: linear-gradient(rgba(9, 210, 197, 1), rgba(0, 48, 143, 1));
    .btns {
      position: absolute;
      bottom: 58px;
      right: 0;
      // border: 1px solid red;
      display: flex;
      flex-direction: column;
      justify-content: center;
      width: 240px;
      // margin-left: 30px;
      padding-right: 45px;
      button {
        // width: ;
        z-index: 1000;
        height: 45px;
        opacity: 0;
        // align-items: center;
      }
    }
  }
  .sebei {
    // width: 100%;
    width: 807px;
    height: 768px;
    // z-index: 10000;
    position: relative;
    // border: 1px solid red;
  }
  .single {
    position: absolute;
    top: -99px;
    left: 123px;
  }
}
</style>
