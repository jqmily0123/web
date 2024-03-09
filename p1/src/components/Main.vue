<template>
  <div class="main">
    <Left></Left>
    <LCenter></LCenter>
    <Right></Right>
  </div>
</template>
<script setup>
import Left from "./Left.vue";
import LCenter from "./LCenter.vue";
import Right from "./Right.vue";
</script>
<style scoped lang="less">
.main {
  display: flex;
  justify-content: space-between;
}
</style>
