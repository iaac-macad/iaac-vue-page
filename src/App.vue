<template>
  <nav class="flex items-center justify-between flex-wrap bg-black/70 p-1">
    <div class="flex items-center flex-shrink-0 text-white mr-6">
      <img class="p-2 h-13" alt="Iaac logo" src="./assets/iaac-white.png" />
      <h2 class="font-semibold text-xl tracking-tight">
        Digital Tools for Cloud-based Data Management
      </h2>
    </div>
  </nav>

  <nav class="flex">
    <Sidebar />
    <GeometryView/>
  </nav>
</template>

<script setup>
import GeometryView from './components/GeometryView.vue'
import Sidebar from "./components/Sidebar.vue";
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
