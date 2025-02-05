<template>
  <div class="chat-area">
    <div class="chat-container">
      <div v-for="(msg, index) in messages" :key="index"
           :class="['message-wrapper', msg.sender === 'me' ? 'message-right' : 'message-left']">
        <div class="message-content">
          <!-- AI 아바타 (왼쪽 메시지일 때만) -->
          <div v-if="msg.sender === 'other'" class="ai-avatar">
            <img :src="'https://hebbkx1anhila5yf.public.blob.vercel-storage.com/Screenshot%202025-02-03%20at%209.14.43%E2%80%AFPM-vUK7BRTcGU1Ln3Abrem1m2c6qIwOnC.png'" alt="AI" class="avatar-img">
          </div>

          <!-- 메시지 내용 -->
          <div class="message-bubble">
            {{ msg.text }}
          </div>
        </div>

        <!-- AI 생성 메시지 메타 정보 -->
        <div v-if="msg.sender === 'other'" class="message-meta">
          AI-generated, for reference only
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  messages: {
    type: Array,
    required: true,
    default: () => []
  }
});
</script>

<style scoped>
.chat-area {
  flex: 1;
  overflow-y: auto;
  padding: 2rem 4rem;
  display: flex;
  flex-direction: column;
  height: calc(100vh - 120px); /* InputArea 높이를 고려한 조정 */
}

.chat-container {
 /* max-width: 1000px;*/
  margin: 0 auto;
  width: 100%;
  display: flex;
  flex-direction: column;
}

.message-wrapper {
  margin-bottom: 2rem;
  width: 100%;
  display: flex;
  flex-direction: column;
}

.message-left {
  align-items: flex-start;
}

.message-right {
  align-items: flex-end;
}

.message-content {
  display: flex;
  align-items: flex-start;
  gap: 0.5rem;
  max-width: 90%; /* 메시지 최대 너비 증가 */
}

.message-left .message-content {
  margin-right: auto;
}

.message-right .message-content {
  margin-left: auto;
  flex-direction: row-reverse;
}

.ai-avatar {
  width: 32px; /* 아바타 크기 증가 */
  height: 32px;
}

.avatar-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.message-bubble {
  padding: 1rem 1.25rem; /* 패딩 증가 */
  border-radius: 12px;
  font-size: 1.2rem; /* 폰트 크기 증가 */
  line-height: 1.6;
}

.message-left .message-bubble {
  background-color: #f8f9fa;
}

.message-right .message-bubble {
  background-color: #e3f2fd;
}

.message-meta {
  font-size: 0.85rem; /* 메타 정보 폰트 크기 증가 */
  margin-top: 0.4rem;
  margin-left: 3rem;
}

/* 스크롤바 스타일링 */
.chat-area::-webkit-scrollbar {
  width: 6px;
}

.chat-area::-webkit-scrollbar-track {
  background: transparent;
}

.chat-area::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, 0.2);
  border-radius: 3px;
}
</style>