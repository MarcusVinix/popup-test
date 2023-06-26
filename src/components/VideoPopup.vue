<script setup>
import { ref } from 'vue'
import TextInput from './TextInput.vue';
import Button from './Button.vue';
import Checkbox from './Checkbox.vue';

defineProps({
  fieldsName: Object,
  videoPopup: Object
})

const optIn = ref(true);
</script>

<template>
<div class="container">
    <h2 class="container__title">{{ videoPopup.title  }}</h2>
  
    <div class="container__video">
      <video :src="videoPopup.urlVideo" controls class="container__video-player"></video>
    </div>
  <span class="container__subtitle">{{ videoPopup.subtitle  }}</span>
  
  <form class="container__form">
    <div class="container__inputs">
      <TextInput 
      v-for="(item, index) in videoPopup.fieldNumber" :key="index"
        :label="fieldsName[index].label"
        :placeholder="fieldsName[index].placeholder"
        :type="fieldsName[index].type"
      >
      </TextInput>
    </div>

    <Checkbox  
      v-if="videoPopup.consentCheckbox"
      v-model:checked="optIn"
      fieldId="optIn"
      label="Permitir coleta de dados">
    </Checkbox>

    <Button></Button>
  </form>

</div>
</template>

<style scoped>
.container {
  background-color: #213547;
  padding: 10px 10px 20px 10px;
  max-height: 800px;
  width: 330px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 15px;
  border-radius: 15px;
}

.container__title {
  color: #b1b1b1;
  font-weight: bold;
  font-size: 1.875rem;;
  margin: 3px 2px;
}

.container__subtitle {
  color: #b1b1b1;
  font-size: 18px;
  font-weight: 400;
}

.container__video {
  width: calc(100% - 31px);
}

.container__video-player {
  width: 100%;
  will-change: filter;
}

.container__inputs {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 15px;
}

.container__form {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 300px;
}

@media (min-width: 800px) {
  .container {
    width: 500px;
  }
  
  .container__form {
    width: 330px;
  }
}
</style>
