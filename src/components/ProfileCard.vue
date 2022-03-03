<script setup>
import { ref } from "@vue/reactivity";
import { computed, onMounted } from "@vue/runtime-core";

const loadUserData = () => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve({
        name: "Name Enam",
        pic: "https://picsum.photos/300",
        bio: "Bio - Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo, non. Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo, non.",
      });
    }, 0);
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
      <p class="profile-info">Lorem, ipsum.</p>
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
  display: flex;
  gap: 1rem;
  width: 100%;
  max-width: 700px;
  min-height: 180px;
  background: whitesmoke;
  margin: 0 auto;
  padding: 30px;
  overflow: hidden;
  border-radius: 20px;
}

.profile-image img {
  max-width: 100%;
  border-radius: 50%;
  border: 5px solid teal;
  padding: 5px;
}

.profile-info {
  text-transform: uppercase;
  color: gray;
}
</style>