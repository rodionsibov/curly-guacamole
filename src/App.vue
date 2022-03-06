<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup

import ProfileCard from "./components/ProfileCard.vue";
import ProfileCardSkeleton from "./components/ProfileCardSkeleton.vue";
</script>

<template>
  <Suspense>
    <template #default>
      <ProfileCard />
    </template>
    <template #fallback>
      <ProfileCardSkeleton />
    </template>
  </Suspense>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333;
}

* {
  box-sizing: border-box;
}

body {
  background: lightgrey;
}

.box {
  height: 4000px;
  border: 2px solid magenta;
  padding: 20px;
}

button {
  display: block;
  padding: 20px;
  margin: 20px 0;
  font-size: 3rem;
  cursor: pointer;
}
</style>
