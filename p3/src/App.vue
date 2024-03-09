<template>
  <div class="app">
    <Layout></Layout>
  </div>
</template>

<script setup>
import Layout from "./components/Layout.vue";
</script>
<style lang="less">
html,
body,
#app,
.app {
  height: 100%;
  width: 100%;
  // z-index: -1;
  display: flex;
  justify-content: center;
  overflow-x: hidden;
  overflow-y: hidden;
}
.app {
  background: url(./assets/2.png) no-repeat;
  background-size: cover;
}
</style>
