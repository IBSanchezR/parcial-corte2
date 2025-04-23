<template>
    <ion-item>
      <ion-label position="floating">Cliente</ion-label>
      <ion-input v-model="clientName"></ion-input>
    </ion-item>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue'
  const clientName = ref('')
  defineEmits(['update:client'])
  watch(clientName, (val) => {
    emit('update:client', val)
  })
  </script>
  