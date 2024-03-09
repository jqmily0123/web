<template>
  <div class="main">
    <div class="left">
      <Left1> </Left1>
    </div>
    <div class="center">
      <Center1></Center1>
    </div>
    <div class="right">
      <Right></Right>
    </div>
  </div>
</template>

<script setup>
import Left1 from "./Left1.vue";
import Center1 from "./Center1.vue";
import Right from "./Right.vue";
</script>
<style scoped lang="less">
.main {
  // width: 900px;
  z-index: 2;
  height: calc(100% - 135px);
  box-sizing: border-box;
  padding: 0 40px;
  display: flex;
  justify-content: space-between;
}
</style>
