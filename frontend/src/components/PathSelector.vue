<template>
    <div class="path-selector">
      <label for="install-path">Путь установки:</label>
      <input
        id="install-path"
        type="text"
        :value="installPath"
        placeholder="Выберите путь..."
        readonly
      />
      <button @click="">Обзор</button>
    </div>
  </template>
  
  <script lang="ts" setup>
  import { defineProps, defineEmits } from 'vue'
  
  // Пропсы и события
  const props = defineProps({
    installPath: String,
  });
  const emit = defineEmits(['updatePath']);
  
  // Функция для вызова диалога выбора пути
  // function browsePath() {
  //   window.backend.Main.BrowsePath().then((path: string) => {
  //     if (path) {
  //       emit('updatePath', path);
  //     }
  //   });
  // }
  </script>
  
  <style scoped>
  .path-selector {
    margin-bottom: 20px;
  }
  </style>
  