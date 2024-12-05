<template>
    <div v-if="message" class="notification">{{ message }}</div>
  </template>
  
  <script>
  export default {
    props: ['message']
  }
  </script>
  
  <style scoped>
  .notification {
    color: green; /* или red для ошибок */
  }
  </style>