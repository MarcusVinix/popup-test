<script setup>
defineProps({
  text: {
    type: String,
    default: 'Submit'
  }
})
</script>

<template>
  <button class="button">{{ text }}</button>
</template>

<style scoped>
.button {
  width: 100%;
  transition: transform 100ms linear; 
}
.button:hover {
  transform: scale(1.05);
  background-color: black;
  border-color: grey;
}
</style>