<script setup>
</script>

<template>
  <div class="profile-card">
    <div class="profile-image"></div>
    <div class="profile-body">
      <p class="profile-info"></p>
      <h2 class="profile-title"></h2>
      <p class="profile-desk"></p>
    </div>
  </div>
</template>

<style scoped>
.profile-card {
  --bg-color: lightgray;
}
 
.profile-card {
  display: flex;
  gap: 1rem;
  width: 100%;
  max-width: 700px;
  min-height: 180px;
  margin: 0 auto;
  padding: 20px;
  overflow: hidden;
  border-radius: 20px;
  background: darkgray;
  opacity: 0.4;
}

.profile-image {
  width: 100px;
  height: 100px;
  margin-top: 16px;
  border-radius: 50%;
  background: var(--bg-color);
}

.profile-body {
  flex-grow: 1;
}

.profile-info {
  height: 24px;
  background: var(--bg-color);
}

.profile-title {
  height: 24px;
  background: var(--bg-color);
}

p {
  background: var(--bg-color);
  height: 24px;
}
</style>