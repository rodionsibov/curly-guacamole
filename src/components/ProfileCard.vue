<script setup>
import { ref } from "@vue/reactivity";
import { computed, onMounted } from "@vue/runtime-core";

const loadUserData = () => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve({
        name: "Name",
        pic: "https://picsum.photos/150",
        bio: "Bio",
      });
    }, 3000);
  });
};

const userData = await loadUserData();
console.log(userData);
</script>

<template>
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
