<script setup>
// This starter template is using Vue 3 <script setup> SFCs

import { ref } from "@vue/reactivity";
import { computed, onMounted } from "@vue/runtime-core";

// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
const loadUserData = () => {
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

const userData = ref(null);

onMounted(async () => {
  userData.value = await loadUserData();
});
</script>

<template>
  
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
