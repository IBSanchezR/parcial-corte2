<template>
    <ion-item>
      <ion-label>Método de Pago</ion-label>
      <ion-select v-model="selected" @ionChange="emit('update:payment', selected)">
        <ion-select-option value="efectivo">Efectivo</ion-select-option>
        <ion-select-option value="tarjeta">Tarjeta</ion-select-option>
      </ion-select>
    </ion-item>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  const selected = ref('')
  defineEmits(['update:payment'])
  </script>
  