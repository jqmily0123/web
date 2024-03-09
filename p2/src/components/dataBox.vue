<template>
  <div class="container">
    <div class="title">{{ title }}</div>
    <div class="data">{{ data }}</div>
    <div class="png">
      <img :src="png" alt="" />
    </div>
    <div class="bgc">
      <img src="../assets/2.png" alt="" />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
  },
  data: {
    type: String,
  },
  png: {
    type: String,
  },
});
</script>
<style scoped lang="less">
.container {
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  position: relative;
  .title {
    color: white;
    font-size: 13px;
    padding: 4px 5px;
  }
  .data {
    color: #fedb65;
    font-size: 21px;
    padding: 4px 5px;
  }
  .bgc {
    width: 100%;
    height: 100%;
    position: absolute;
    left: 0;
    top: 0;
  }
}
</style>
