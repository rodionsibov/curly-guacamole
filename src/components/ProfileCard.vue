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

<style scoped>
.profile-card {
  width: 100%;
  max-width: 700px;
  min-height: 180px;
  background: white;
  margin: 0 auto;
  padding: 30px;
  box-sizing: border-box;
  overflow: hidden;
  border-radius: 20px;
}
</style>