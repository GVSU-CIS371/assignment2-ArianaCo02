<template>
  <div class="mug">
    <slot />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.mug {
  /* mug shape and layout */
  width: 220px;
  height: 300px;
  border-radius: 0 0 50px 50px;
  position: relative;
  overflow: hidden;

  /* pink mug color */
  background-color: pink;


  border: 4px solid #b56576;   /* darker pink edge */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  margin: 20px auto;
}
</style>

