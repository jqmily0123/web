<template>
  <div class="app">
    <div class="layout">
      <Layout></Layout>
    </div>
  </div>
</template>
<script setup>
import Layout from "./view/Layout.vue";
</script>
<style lang="less">
#app,
.app,
html,
body {
  height: 100%;
  width: 100%;
  overflow-y: hidden;
}
.app {
  height: 100%;
  display: flex;
  justify-content: center;
  background-color: #030c31;
  min-height: 1920px;
}
</style>
