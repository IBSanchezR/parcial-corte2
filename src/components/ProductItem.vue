<template>
    <ion-card>
      <ion-card-header>
        <ion-card-title>{{ product.name }}</ion-card-title>
      </ion-card-header>
      <ion-card-content>
        <p>Precio: ${{ product.price }}</p>
        <ion-button @click="$emit('add-to-cart', product)">Agregar</ion-button>
      </ion-card-content>
    </ion-card>
  </template>
  
  <script setup>
  defineProps(['product'])
  defineEmits(['add-to-cart'])
  </script>
  