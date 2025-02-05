<template>
  <div class="input-area">
    <div class="message-input">
      <input
          type="text"
          class="form-control border-0"
          placeholder="Message DeepSeek"
          v-model="message"
          @keydown.enter="sendMessage"
      >
      <div class="input-actions">
        <button class="btn btn-link text-dark p-1">
          <i class="bi bi-search fs-5"></i>
        </button>
        <button class="btn btn-link text-dark p-1">
          <i class="bi bi-paperclip fs-5"></i>
        </button>
        <button class="btn btn-link text-dark p-1">
          <i class="bi bi-arrow-up-circle-fill fs-5"></i>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, defineEmits } from "vue";

const message = ref("");
const emit = defineEmits(["send-message"]);

const sendMessage = () => {
  if (message.value.trim() !== "") {
    console.log(message)
    emit("send-message", message.value); // ✅ 부모로 메시지 전달
    message.value = "";
  }
};
</script>

<style scoped>
/* Input area styles */
.input-area {
  padding: 24px;
}

.message-input {
  display: flex;
  align-items: center;
  background-color: white;
  border: 1px solid #dee2e6;
  border-radius: 50px;
  padding: 4px;
}

.message-input .form-control {
  border-radius: 50px;
  font-size: 30px;
}

.input-actions {
  display: flex;
  align-items: center;
  padding: 0 12px;
  gap: 8px; /* 아이콘 간 간격 조정 */
}

.input-actions .btn {
  padding: 8px;  /* 버튼 패딩 증가 */
}

/* Bootstrap의 fs-5 클래스로 아이콘 크기를 키웁니다 */
.fs-5 {
  font-size: 2.5rem !important;
}

/* Remove focus outline */
.form-control:focus {
  box-shadow: none;
}

.btn-link {
  text-decoration: none;
}
</style>