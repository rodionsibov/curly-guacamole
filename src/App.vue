<script setup>
// This starter template is using Vue 3 <script setup> SFCs

import { ref } from "@vue/reactivity";

// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
const loadUserData = async () => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve({
        name: "Name Eman",
        pic: null,
        bio: null,
      });
    }, 2000);
  });
};

const userData = ref(await loadUserData());
</script>

<template>
  <div class="profile-card">
    <div class="profile-image">
      <img :src="userData.pic" alt="">
    </div>
    <div class="profile-info">
      <span>Written By</span>
      <h3>
        {{userData.name}}
      </h3>
    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
