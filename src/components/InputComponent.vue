<script setup>
import { ref } from 'vue';

const inputValue = ref('');
</script>

<template>
  <input type="text" v-model="inputValue">
  <div class="input-result">{{ inputValue }}</div>
</template>

<style scoped>

</style>
