<script setup lang="ts">
const charset = '23456789abcdefghjkmnpqrtuvwxyzABCDEFGHJKLMNPQRSTUVWXYZ';
const count = ref('');
const copyToClipBoard = () => {};
const changePassword = () => {
  let p: string = '';
  for (let i = 0; i < 10; i++) {
    const rand: number = Math.floor(Math.random() * charset.length);
    p += charset[rand];
  }
  count.value = p;
};
</script>

<template>
  <div>
    <h1>ReadablePass</h1>
    <div id="pass-container">{{ count }}</div>
    <button @click="changePassword">Change</button>
  </div>
</template>
