<script setup>
import { PhCheckSquare, PhSquare } from "@phosphor-icons/vue"
defineProps({
  label: String,
  fieldId: {
    type: String,
    required: true,
  },
  checked: {
    type: Boolean
  }
})
</script>

<template>
 <input
    @input="(event) => $emit('update:checked', event.target.checked)"
    type="checkbox"
    :checked="checked"
    :id="fieldId"
    class="inputCheckBox"
  />
  <label
    :for="fieldId"
    class="label"
  >
    <PhCheckSquare v-if="checked" :size="32" />
    <PhSquare v-if="!checked" :size="32" />
    {{ label }}
  </label>
</template>

<style scoped>
.inputCheckBox {
  margin-right: 0.5rem;
  display: none;
}

.label {
  display: flex;
  flex-direction: row;
  align-items: center;
  font-weight: 500;
  color: rgba(228, 228, 228, 0.739);;
  cursor: pointer;
  user-select: none;
}
</style>