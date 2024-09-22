<script setup lang="ts">
  import LeftContent from './components/LeftContent/index.vue';
  import RightContent from './components/RightContent/index.vue';

</script>

<template>
  <div class="app-container">
    <left-content class="left-container"></left-content>
    <right-content class="right-container"></right-content>
  </div>
</template>

<style scoped>
  .app-container {
    display: flex;

    .left-container {
      width: 70%;
      border: 1px solid gainsboro;
    }

    .right-container {
      width: 30%
    }
  }

</style>
