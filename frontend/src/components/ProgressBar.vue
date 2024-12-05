<template>
    <div class="progress-container">
      <label>Прогресс установки:</label>
      <div class="progress-bar">
        <div
          class="progress-fill"
          :style="{ width: progress + '%' }"
        ></div>
      </div>
      <p>{{ progress }}%</p>
    </div>
  </template>
  
  <script lang="ts" setup>
  import { defineProps } from 'vue'
  
  const props = defineProps({
    progress: Number,
  });
  </script>
  
  <style scoped>
  .progress-container {
    margin: 20px 0;
  }
  
  .progress-bar {
    width: 100%;
    height: 20px;
    background: #e0e0e0;
    border-radius: 10px;
    overflow: hidden;
    position: relative;
  }
  
  .progress-fill {
    height: 100%;
    background: #76c7c0;
    transition: width 0.5s ease;
  }
  </style>
  