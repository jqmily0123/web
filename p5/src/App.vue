<template>
  <div class="app">
    <Layout class="layout"></Layout>
  </div>
</template>
<script setup>
import Layout from "./views/Layout.vue";
</script>
<style lang="less">
* {
  padding: 0;
  margin: 0;
}
#app,
html,
body,
.app {
  width: 100%;
  height: 100%;
  overflow-x: hidden;
  overflow-y: hidden;
}
.app {
  background-color: #000;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  img {
    position: relative;
    top: 0;
    left: 0;
  }
}
</style>
