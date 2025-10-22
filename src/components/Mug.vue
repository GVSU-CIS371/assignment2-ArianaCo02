<template>
  <div class="mug">
    <slot />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.mug {
  width: 220px;
  height: 300px;
  background-color: #ffc0cb; /* soft pink */
  border: 4px solid #b56576; /* darker pink outline */
  border-radius: 0 0 50px 50px; /* round bottom like a mug */
  position: relative;
  overflow: hidden;
  margin: 20px auto;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

/* ☕ the handle */
.mug::after {
  content: "";
  position: absolute;
  right: -40px;          
  top: 80px;            
  width: 70px;          
  height: 120px;        
  border: 8px solid #b56576; 
  border-radius: 60%;    
  background-color: transparent; 
}
</style>


