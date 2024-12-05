<template>
  <div class="app">
    <h1>Программа установки</h1>

    <!-- Компонент выбора пути -->
    <PathSelector
      :installPath="installPath"
      @updatePath="updatePath"
    />

    <!-- Прогресс-бар -->
    <ProgressBar :progress="progress" />

    <!-- Кнопка запуска установки -->
    <InstallButton
      :isInstalling="isInstalling"
      @startInstallation="startInstallation"
    />
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

// Импорт компонентов
import PathSelector from './components/PathSelector.vue'
import ProgressBar from './components/ProgressBar.vue'
import InstallButton from './components/InstallButton.vue'

const installPath = ref<string>(''); // Путь установки
const progress = ref<number>(0); // Прогресс
const isInstalling = ref<boolean>(false); // Флаг установки

// Обновление пути установки
function updatePath(newPath: string) {
  installPath.value = newPath;
}

// Начало установки
function startInstallation() {
  if (!installPath.value) {
    alert('Выберите путь для установки!');
    return;
  }

  isInstalling.value = true;
  progress.value = 0;

  // Эмуляция процесса установки
  const interval = setInterval(() => {
    if (progress.value >= 100) {
      clearInterval(interval);
      isInstalling.value = false;
      alert('Установка завершена!');
      // window.backend.Main.OpenPath(installPath.value); // Открыть проводник
    } else {
      progress.value += 10;
    }
  }, 500);
}
</script>

<style scoped>
.app {
  font-family: Arial, sans-serif;
  max-width: 400px;
  margin: 20px auto;
  text-align: center;
}
</style>
