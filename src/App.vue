<script setup>
import VideoPopup from './components/VideoPopup.vue';
import PopupGame from './components/PopupGame.vue'
import config from './popup-config.json'


const fieldsName = [
  {placeholder: 'Email', label: 'E-mail', type: 'email'},
  {placeholder: 'Nome', label: 'Nome', type: 'text'},
  {placeholder: 'Número de celular', label: 'Celular',  type: 'text'},
  {placeholder: 'Gênero', label: 'Gênero', type: 'text'}
]

if (config.gamePopup.fieldNumber > 4)
  config.gamePopup.fieldNumber = 4;
if (config.videoPopup.fieldNumber > 4)
  config.videoPopup.fieldNumber = 4;

</script>

<template>
  <div class="app">
    <PopupGame 
    v-if="config.show == config.gamePopup.id"
    :fieldsName="fieldsName"
    :gamePopup="config.gamePopup"
    />
    <VideoPopup 
    v-if="config.show == config.videoPopup.id"
    :fieldsName="fieldsName"
    :videoPopup="config.videoPopup"
    />
  </div>
</template>

<style scoped>
.app {
  text-align: center;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

</style>
