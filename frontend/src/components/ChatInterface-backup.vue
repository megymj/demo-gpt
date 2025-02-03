<template>
  <div class="app-container">
    <!-- Sidebar -->
    <div class="sidebar">
      <!-- Header -->
      <div class="sidebar-header">
        <h5 class="m-0">deepseek</h5>
        <button class="btn btn-link ms-2 p-0 text-dark">
          <i class="bi bi-clipboard"></i>
        </button>
      </div>

      <!-- New Chat Button -->
      <div class="new-chat-btn">
        <button class="btn btn-light rounded-3 w-100 text-start py-2">
          <i class="bi bi-plus-circle me-2"></i>
          New chat
        </button>
      </div>

      <!-- Chat List -->
      <div class="chat-list">
        <div class="mb-4">
          <div class="text-muted small mb-2">Today</div>
          <div class="chat-item">New chat</div>
        </div>

        <div>
          <div class="text-muted small mb-2">7 Days</div>
          <div class="chat-items">
            <div class="chat-item">New chat</div>
            <div class="chat-item">New chat</div>
            <div class="chat-item">New chat</div>
            <div class="chat-item">New chat</div>
            <div class="chat-item">AWS에서 Lambda 환경에 Spring Boo...</div>
          </div>
        </div>
      </div>

      <!-- Bottom Actions -->
      <div class="bottom-actions">
        <div class="get-app-btn">
          <button class="btn btn-light rounded-3 w-100 text-start py-2">
            <i class="bi bi-phone me-2"></i>
            Get App
            <span class="badge bg-primary rounded-pill ms-1 px-2">NEW</span>
          </button>
        </div>
        <div class="profile-section">
          <div class="rounded-circle bg-secondary" style="width: 28px; height: 28px;"></div>
          <span class="ms-2">My Profile</span>
        </div>
      </div>
    </div>

    <!-- Main Content -->
    <div class="main-content">
      <!-- Chat Area -->
      <div class="chat-area">
        <img :src="'https://hebbkx1anhila5yf.public.blob.vercel-storage.com/Screenshot%202025-02-03%20at%209.14.43%E2%80%AFPM-vUK7BRTcGU1Ln3Abrem1m2c6qIwOnC.png'" alt="DeepSeek Logo" class="mb-3" style="width: 40px; height: 40px;">
        <h4 class="mb-2">Hi, I'm DeepSeek.</h4>
        <p class="text-muted">How can I help you today?</p>
      </div>

      <!-- Input Area -->
      <div class="input-area">
        <div class="message-input">
          <input 
            type="text" 
            class="form-control border-0"
            placeholder="Message DeepSeek"
          >
          <div class="input-actions">
            <button class="btn btn-link text-dark p-1 d-flex align-items-center">
              <i class="bi bi-robot me-1"></i>
              <span class="small">DeepThink (R1)</span>
            </button>
            <button class="btn btn-link text-dark p-1">
              <i class="bi bi-search"></i>
            </button>
            <button class="btn btn-link text-dark p-1">
              <i class="bi bi-paperclip"></i>
            </button>
            <button class="btn btn-link text-dark p-1">
              <i class="bi bi-arrow-up-circle-fill"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Component logic can be added here if needed
</script>


<style scoped>
/* Reset default margins and set full height */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Main container */
.app-container {
  display: flex;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

/* Sidebar styles */
.sidebar {
  width: 280px;
  height: 100%;
  display: flex;
  flex-direction: column;
  background-color: white;
  border-right: 1px solid #dee2e6;
}

.sidebar-header {
  padding: 16px;
  display: flex;
  align-items: center;
}

.new-chat-btn {
  padding: 0 16px 12px 16px;
}

.chat-list {
  flex: 1;
  overflow-y: auto;
  padding: 0 16px;
}

.chat-item {
  padding: 8px 12px;
  margin: 2px 0;
  border-radius: 6px;
  cursor: pointer;
  color: #333;
}

.chat-item:hover {
  background-color: #f8f9fa;
}

.bottom-actions {
  border-top: 1px solid #dee2e6;
  padding: 12px 0;
  margin-top: auto;
}

.get-app-btn {
  padding: 0 16px 8px 16px;
}

.profile-section {
  padding: 8px 16px;
  display: flex;
  align-items: center;
}

/* Main content styles */
.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  background-color: #f8f9fa;
}

.chat-area {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

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
}

.input-actions {
  display: flex;
  align-items: center;
  padding: 0 8px;
}

/* Remove focus outline */
.form-control:focus {
  box-shadow: none;
}

.btn-link {
  text-decoration: none;
}

/* Hide scrollbar for Chrome, Safari and Opera */
.chat-list::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.chat-list {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>