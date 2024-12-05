<template>
    <div>
      <p>Загрузка файлов...</p>
      <ProgressBar :progress="progress" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        progress: 0
      }
    },
    methods: {
      startDownload() {
        // Логика загрузки файлов с обновлением прогресса
      }
    }
  }
  </script>