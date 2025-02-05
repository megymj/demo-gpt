<template>
  <div class="app-container">
    <Sidebar/>
    <div class="main-content">
      <ChatArea :messages="messages" />
      <InputArea @send-message="handleSendMessage" />
    </div>
  </div>
</template>

<script setup>
import Sidebar from "@/components/Sidebar.vue";
import ChatArea from "@/components/ChatArea.vue";
import InputArea from "@/components/InputArea.vue";
import {ref} from 'vue';

const messages = ref([
  { text: "안녕하세요!", sender: "other" },
  { text: "간단한 채팅 UI 테스트 중입니다.", sender: "other" },
]);

const handleSendMessage = (message) => {
  messages.value.push({ text: message, sender: "me" });
};
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