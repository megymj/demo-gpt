<template>
  <div class="sidebar">
    <div class="sidebar-header">
      <h5 class="m-0">deepseek</h5>
      <button class="btn btn-link ms-2 p-0 text-dark">
        <i class="bi bi-clipboard"></i>
      </button>
    </div>
    <div class="new-chat-btn">
      <button class="btn btn-light rounded-3 w-100 text-start py-2">
        <i class="bi bi-plus-circle me-2"></i>
        New chat
      </button>
    </div>
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
</template>

<script setup>
// Component logic can be added here if needed
</script>

<style scoped>
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