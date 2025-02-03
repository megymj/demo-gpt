<template>
  <div class="app-container">
    <Sidebar />
    <div class="main-content">
      <ChatArea />
      <InputArea />
    </div>
  </div>
</template>

<script setup>
import Sidebar from './Sidebar.vue';
import ChatArea from './ChatArea.vue';
import InputArea from './InputArea.vue';
</script>

<style scoped>

/* Main container */
.app-container {
  display: flex;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

/* Main content styles */
.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  background-color: #f8f9fa;
}
</style>