<script setup>
import { ref } from "@vue/reactivity";
import { computed, onMounted } from "@vue/runtime-core";

const loadUserData = () => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve({
        name: "Name Enam",
        pic: "https://picsum.photos/200",
        bio: "Bio - Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo, non. Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo, non.",
      });
    }, 1000);
  });
};

const userData = await loadUserData();
console.log(userData);
</script>

<template>
  <div class="profile-card" v-if="userData">
    <div class="profile-image">
      <img :src="userData.pic" alt="" />
    </div>
    <div class="profile-body">
      <p class="profile-info">Lorem, ipsum</p>
      <h2>
        {{ userData.name }}
      </h2>
      <p>
        {{ userData.bio }}
      </p>
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
  min-width: 100px;
  border-radius: 50%;
  border: 5px solid teal;
  padding: 5px;
}

.profile-info {
  text-transform: uppercase;
  color: gray;
  letter-spacing: 2px;
  font-size: small;
}

p {
  color: gray;
}
</style>