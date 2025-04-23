<template>
    <ion-page>
      <ion-header>
        <ion-toolbar><ion-title>Facturación</ion-title></ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <invoice-header @update:client="client = $event" />
        <payment-selector @update:payment="payment = $event" />
        
        <product-item 
          v-for="p in products" 
          :key="p.id" 
          :product="p" 
          @add-to-cart="cart.push($event)"
        />
  
        <ion-button expand="block" @click="crearFactura">Crear Factura</ion-button>
      </ion-content>
    </ion-page>
  </template>
  
  <script setup>
  import InvoiceHeader from '@/components/InvoiceHeader.vue'
  import PaymentSelector from '@/components/PaymentSelector.vue'
  import ProductItem from '@/components/ProductItem.vue'
  import { ref } from 'vue'
  
  const client = ref('')
  const payment = ref('')
  const cart = ref([])
  
  const products = ref([
    { id: 1, name: 'Producto A', price: 100 },
    { id: 2, name: 'Producto B', price: 150 }
  ])
  
  function crearFactura() {
    console.log('Cliente:', client.value)
    console.log('Pago:', payment.value)
    console.log('Carrito:', cart.value)
  }
  </script>
  