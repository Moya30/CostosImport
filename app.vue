<!-- <template>
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
</style> -->
<template>
  <div class="container">
    <h1>Calculadora de Costo de Producto</h1>
    <form @submit.prevent="calculateTotal" class="form">
      <div class="input-group">
        <label for="productPrice">Precio del producto:</label>
        <input type="number" id="productPrice" v-model.number="productPrice" />
      </div>
      <div class="input-group">
        <label for="taxes">Taxes:</label>
        <input type="number" id="taxes" v-model.number="taxes" />
      </div>
      <div class="input-group">
        <label for="fixedTax">Impuesto aproximado (24%, fijo):</label>
        <input type="number" id="fixedTax" v-model.number="fixedTax" disabled />
      </div>
      <div class="input-group">
        <label for="shippingCost">Costo de envío ($30, fijo):</label>
        <input type="number" id="shippingCost" v-model.number="shippingCost" disabled />
      </div>
      <div class="input-group">
        <button type="submit">Calcular costo total</button>
      </div>
    </form>
    <div v-if="totalCost !== null" class="result">
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
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background-color: #f5f5f5;
  padding: 20px;
  box-sizing: border-box;
}

.form {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 300px;
}

.input-group {
  margin-bottom: 15px;
}

.input-group label {
  display: block;
  margin-bottom: 5px;
}

.input-group input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.result {
  margin-top: 20px;
  background: #e3f2fd;
  padding: 10px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>
