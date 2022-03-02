<script setup>
// This starter template is using Vue 3 <script setup> SFCs

import { ref } from "@vue/reactivity";
import { computed, onMounted } from "@vue/runtime-core";

// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
const loadUserData = () => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve({
        name: "Name",
        pic: 'https://picsum.photos/300',
        bio: 'Bio',
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
  <Suspense>
    <template #default>
      <div class="profile-card" v-if="userData">
        <div class="profile-image">
          <img :src="userData.pic" alt="" />
          <h3>
            {{ userData.name }}
          </h3>
          <p>
            {{ userData.bio }}
          </p>
        </div>
      </div>
    </template>
    <template #fallback>Loading...</template>
  </Suspense>
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
