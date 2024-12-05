<template>
    <button @click="startInstallation" :disabled="isInstalling">
      {{ isInstalling ? "Устанавливается..." : "Начать установку" }}
    </button>
  </template>
  
  <script lang="ts" setup>
  import { defineProps, defineEmits } from 'vue'
  
  // Пропсы и события
  const props = defineProps({
    isInstalling: Boolean,
  });
  const emit = defineEmits(['startInstallation']);
  
  // Вызов события начала установки
  function startInstallation() {
    emit('startInstallation');
  }
  </script>
  
  <style scoped>
  button {
    width: 100%;
    height: 40px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    margin-top: 20px;
  }
  
  button:disabled {
    background-color: gray;
    cursor: not-allowed;
  }
  </style>
  