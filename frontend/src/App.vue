<template>
  <div class="app-container">
    <Sidebar/>
    <div class="main-content">
      <!-- 초기 환영 메시지를 보여주는 조건부 렌더링 -->
      <div v-if="messages.length === 0" class="welcome-message">
        <img :src="'https://hebbkx1anhila5yf.public.blob.vercel-storage.com/Screenshot%202025-02-03%20at%209.14.43%E2%80%AFPM-vUK7BRTcGU1Ln3Abrem1m2c6qIwOnC.png'" alt="DeepSeek Logo" class="mb-3" style="width: 40px; height: 40px;">
        <h4 class="mb-2">Hi, I'm DeepSeek.</h4>
        <p class="text-muted">How can I help you today?</p>
      </div>

      <!-- 메시지가 있을 때 ChatArea 표시 -->
      <ChatArea v-else :messages="messages" />
      <InputArea @send-message="handleSendMessage" />
    </div>
  </div>
</template>

<script setup>
import Sidebar from "@/components/Sidebar.vue";
import ChatArea from "@/components/ChatArea.vue";
import InputArea from "@/components/InputArea.vue";
import {ref} from 'vue';

const messages = ref([]);

const handleSendMessage = async (message) => {
  // 사용자 메시지 추가
  messages.value.push({
    text: message,
    sender: "me"
  });

  // AI 응답 시뮬레이션 (실제로는 API 호출 등으로 대체)
  await new Promise(resolve => setTimeout(resolve, 1000));

  messages.value.push({
    text: `You said: ${message}`,
    sender: "other"
  });
};
</script>

<style scoped>
.app-container {
  display: flex;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  background-color: #f8f9fa;
}

.welcome-message {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>