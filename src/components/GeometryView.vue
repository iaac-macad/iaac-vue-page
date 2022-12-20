<template>
    <div id="viewport" class="flex flex-col p-4"></div>
</template>

<script setup>
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