<template>
  <div class="header">
    <img src="../assets/1kLR.gif" />
    <h1>Teo's kitchen</h1>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
h1 {
  position: relative;
  color: black;
  text-align: left;
  width: fit-content;
  font-weight: 600;
}

.header {
  display: flex;
  align-items: center;
  /* justify-content: space-between; */
  /* background-color: var(--vt-c-primary); */
  background-color: #91c6bc;
  width: 100%;
  height: 92px;
  left: 0;
  top: 0;
  position: fixed;
}

img {
  padding-top: 10px;
}
</style>
