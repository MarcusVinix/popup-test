<script setup>

defineProps({
  label: {
    type: String,
    default: 'Name',
  },
  placeholder: {
    type: String,
    default: 'Name'
  },
  type: {
    type: String,
    default: 'text'
  }
})

</script>

<template>
  <div class="textInput__root">
    <span class="textInput__root__label">{{ label }}</span>
    <input class="textInput__root__input" :placeholder="placeholder" :type="type"/>
  </div>
</template>

<style scoped>
.textInput__root {
  display: flex;
  align-items: start;
  flex-direction: column;
  height: 3rem;
  border-radius: 5px;
  background-color: gray;
  width: calc(100% - 20px);
  padding: 3px 10px;
}

.textInput__root__input {
  background-color: transparent;
  flex: 1 1 0%;
  color: rgba(228, 228, 228, 0.739);
  font-weight: 500;
  outline: none;
  font-size: 14px;
  box-shadow: none;
  border: none;
}

.textInput__root__input::placeholder {
    color: rgba(228, 228, 228, 0.739);
    font-weight: 700;
}

.textInput__root__label {
  font-size: 12px;
  display: flex;
  padding-left: 2px;
  color: rgba(228, 228, 228, 0.739);
}
</style>
