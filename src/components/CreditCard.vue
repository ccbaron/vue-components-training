<template>
    <div class="card" :style="{ backgroundColor: bgColor, color: color }">
      <div class="type">
        <img v-if="type==='Visa'" alt="Visa" src="https://upload.wikimedia.org/wikipedia/commons/0/04/Visa.svg">
        <img v-else alt="Master Card" src="https://upload.wikimedia.org/wikipedia/commons/2/2a/Mastercard-logo.svg">
      </div>
      <div class="number">•••• •••• •••• {{ last4 }}</div>
      <div class="meta">
        <span>Expires {{ expirationMonthPadded }}/{{ String(expirationYear).slice(-2) }}</span>
        <span class="bank">{{ bank }}</span>
      </div>
      <div class="owner">{{ owner }}</div>
    </div>
  </template>
  
  <script>
  // Componente para mostrar una tarjeta de crédito con detalles y estilo personalizado
  export default {
    name: 'CreditCard',
    props: {
      type: String, number: String, expirationMonth: Number, expirationYear: Number,
      bank: String, owner: String, bgColor: String, color: String
    },
    computed: {
      last4() { return this.number?.slice(-4) ?? ''; },
      expirationMonthPadded() { return String(this.expirationMonth).padStart(2, '0'); }
    }
  }
  </script>
  
  <style scoped>
  .card { 
    width:320px; 
    border-radius:10px; 
    padding:18px; 
    display:flex; 
    flex-direction:column; 
    gap:10px 
  }

  .type { 
    display:flex; 
    justify-content:flex-end 
  }

  .type img { 
    height:22px 
  }

  .number { 
    font-size:1.4rem; 
    letter-spacing:3px 
  }

  .meta { 
    display:flex; 
    gap:10px; 
    font-size:.9rem; 
    opacity:.9 
  }

  .owner { 
    font-weight:600 
  }
  </style>
  