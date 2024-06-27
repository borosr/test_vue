<script setup lang="ts">
</script>

<template>
  <div class="nice-btn">
    <slot />
  </div>
</template>

<style scoped>
.nice-btn {
  width: 100px;
  height: 30px;
  background-color: #888888;
  color: #181818;
  border-radius: 5px;
  cursor: pointer;

  display: flex;
  justify-content: center;
  align-items: center;
  &:hover {
    background-color: #555555;
  }
}
</style>
