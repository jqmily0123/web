<template>
  <div id="3dContainer" style="width: 792px; height: 500px;border: 1px solid pink;overflow: hidden"></div>
</template>

<script setup>
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";
import gsap from "gsap";
import * as dat from "dat.gui";
import { onMounted } from "vue";
import { FBXLoader } from "three/examples/jsm/loaders/FBXLoader.js";
import { RGBELoader } from "three/examples/jsm/loaders/RGBELoader.js";

import { MeshStandardMaterial, SpotLight } from "three";

onMounted(() => {
  const container = document.getElementById("3dContainer");
  const { width, height } = container.style;
  const widthN = width.slice(0, width.length - 2);
  const heightN = height.slice(0, height.length - 2);
  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(75, widthN / heightN, 0.01, 300000);
  camera.position.set(0, 0, 10000);
  scene.add(camera);
  //添加环境光源
  const light = new THREE.AmbientLight( 0xffffff,0.05); // soft white light
  scene.add( light );
  //添加直射光源
  const directionalLight = new THREE.DirectionalLight( 0xffffff, 0.3 );
  scene.add( directionalLight );

  //添加场景
  scene.background = new THREE.Color(0x333333)

  const fbxLoader = new FBXLoader()
  fbxLoader.load('123.fbx',(item)=>{
    console.log(item);
    // item.children[0].material.depthTest = false;
    item.children[0].material.depthWrite = true;
    item.children[0].size = THREE.DoubleSide;
    scene.add(item)
  })

  const renderer = new THREE.WebGLRenderer({
    antialias:true,
    // antialias:true,
    alpha:true,
    logarithmicDepthBuffer: true
  });
  renderer.setSize(widthN, heightN);
  // renderer.an

  // console.log(renderer);

  //添加辅助坐标器
  const axisHelper = new THREE.AxesHelper(5);
  scene.add(axisHelper);
  // const loader = new OBJLoader();
  // const mtlLoader = new MTLLoader();
  // loader.load("设计1.obj", function (geometry) {
  //   scene.add(geometry);
  //   // renderer.render(scene, camera);
  // });
  //创建轨道控制器
  const controls = new OrbitControls(camera, renderer.domElement);
  //设置控制器阻尼
  controls.enableDamping = true;

  container.appendChild(renderer.domElement);

  const render = () => {
    var vector = camera.position.clone();
    //console.log(vector.x);
    directionalLight.position.set(vector.x,vector.y,vector.z);
    controls.update();
    renderer.render(scene, camera);
    requestAnimationFrame(render);
    // console.log(time);
  };
  render();
  window.addEventListener("dblclick", () => {
    //判断当前是否处于全屏状态
    const fullScreenElement = document.fullscreenElement;
    if (!fullScreenElement) {
      renderer.domElement.requestFullscreen();
    } else {
      document.exitFullscreen();
    }
  });
});
// 设置时钟

</script>
<style scoped lang="less"></style>
