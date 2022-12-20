<template>
    <div id="viewport" class="flex flex-col p-4">
      <button
      class="
        bg-blue-500
        hover:bg-blue-400
        text-white
        font-bold
        py-2
        px-4
        border-b-4 border-blue-700
        hover:border-blue-500
        rounded
      "
      @click="initScene"
    >
      do something with threejs
    </button>
    <div id="threejs-container" class="py-5"></div>
    </div>
</template>

<script setup>
// Imports;
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";


// Three js objects
let renderer = null;
let camera = null;
let scene = null;
let controls = null;

function initScene()
{  
  let width = 500;
  let heigh = 700;

  // rendeder
  renderer = new THREE.WebGLRenderer();
  renderer.setSize(width, heigh);
  renderer.setPixelRatio(window.devicePixelRatio);
  document.getElementById("threejs-container").appendChild(renderer.domElement);

  // camera
  camera = new THREE.PerspectiveCamera(75, width / heigh, 0.1, 1000);
  camera.position.set(0, 0, 40);

  // scene
  scene = new THREE.Scene();
  scene.background = new THREE.Color("#f5f6fa");

  // orbit controls
  controls = new OrbitControls(camera, renderer.domElement);
  
  // add fun shape
  const geometry = new THREE.TorusKnotGeometry(8, 3, 150, 16);
  const material = new THREE.MeshNormalMaterial();
  const shape = new THREE.Mesh(geometry, material);
  scene.add(shape);
  animate();
}

// for controls update
function animate() {
  requestAnimationFrame(animate);
  controls.update();
  renderer.render(scene, camera);
}

</script>

<style scoped>
#viewport {
  border-style: dashed;
  border-color: #d2dfe8;
  border-width: 4px;
  border-radius: 10px;
  margin: 12px;
  height: calc(100vh - 105px);
  width: calc(100vw - 105px);
  min-width: 200px;
}
</style>