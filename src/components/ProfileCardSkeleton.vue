<script setup>
</script>

<template>
  <div class="profile-card">
    <div class="profile-image">
      <img />
    </div>
    <div class="profile-body">
      <p class="profile-info"></p>
      <h2></h2>
      <p></p>
    </div>
  </div>
</template>

<style scoped>
.profile-card {
  display: flex;
  gap: 1rem;
  width: 100%;
  max-width: 700px;
  min-height: 180px;
  background: whitesmoke;
  margin: 0 auto;
  padding: 20px;
  overflow: hidden;
  border-radius: 20px;
}

.profile-image img {
  width: 100%;
  padding-top: 100%;
  background-color: #eee;
}

.profile-info {
  width: 100%;
  height: 24px;
  background-color: #eee;
}

p {
  width: 80%;
  height: 16px;
}
</style>