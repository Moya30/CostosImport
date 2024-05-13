<template>
    <div>
      <h1>Calculadora de Costo de Producto</h1>
      <form @submit.prevent="calculateTotal">
        <div>
          <label for="productPrice">Precio del producto:</label>
          <input type="number" id="productPrice" v-model.number="productPrice" />
        </div>
        <div>
          <label for="taxes">Taxes:</label>
          <input type="number" id="taxes" v-model.number="taxes" />
        </div>
        <div>
          <label for="fixedTax">Impuesto aproximado (24%, fijo):</label>
          <input type="number" id="fixedTax" v-model.number="fixedTax" disabled />
        </div>
        <div>
          <label for="shippingCost">Costo de envío ($30, fijo):</label>
          <input type="number" id="shippingCost" v-model.number="shippingCost" disabled />
        </div>
        <div>
          <button type="submit">Calcular costo total</button>
        </div>
      </form>
      <div v-if="totalCost !== null">
        <h2>Costo Total: ${{ totalCost.toFixed(2) }}</h2>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        productPrice: 0,
        taxes: 0,
        fixedTax: 24,
        shippingCost: 30,
        totalCost: null
      };
    },
    methods: {
      calculateTotal() {
        const taxAmount = this.productPrice * (this.fixedTax / 100);
        const subtotal = this.productPrice + this.taxes + taxAmount;
        this.totalCost = subtotal + this.shippingCost;
      }
    }
  }
  </script>
  
  <style>
  /* Agrega estilos aquí si es necesario */
  </style>
  