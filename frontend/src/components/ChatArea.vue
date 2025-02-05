<template>
  <div class="chat-area">
    <div class="chat-box">
      <div v-for="(msg, index) in messages" :key="index" class="message">
        <p :class="msg.sender === 'me' ? 'my-message' : 'other-message'">
          {{ msg.text }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>

defineProps({
  messages: Array, // ✅ 부모에서 받은 messages
});

</script>

<style scoped>
.chat-area {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.chat-box {
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

.message {
  padding: 10px;
  margin: 5px 0;
  border-radius: 5px;
  color: black;
  font-size: 20px;
}

.my-message {
  background-color: #d1e7dd;
  align-self: flex-end;
}

.other-message {
  background-color: #f8d7da;
  align-self: flex-start;
}
</style>