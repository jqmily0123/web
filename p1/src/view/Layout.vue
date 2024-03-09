<template>
  <div class="mlayout">
    <Header></Header>
    <Main></Main>
  </div>
</template>
<script setup>
import Header from "../components/Header.vue";
import Main from "../components/Main.vue";
</script>
<style scoped lang="less">
.mlayout {
  width: 100%;
  height: 1080px;

  margin: 0 auto;
}
</style>
