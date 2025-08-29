<template>
    <div class="grid">
      <div v-for="n in limit" :key="n" :class="{ even: n%2===0 }">{{ n }}</div>
    </div>
  </template>

  <script>
  // Componente para mostrar una tabla de números con estilo para números pares
  export default { name:'NumbersTable', props:{ limit:{ type:Number, required:true } } }
  </script>

  <style scoped>

  .grid { 
    display:grid; 
    grid-template-columns: repeat(auto-fill, minmax(60px,1fr)); 
    gap:6px 
  }

  .grid > div { 
    padding:10px; 
    border:1px solid #ddd; 
    text-align:center; 
    border-radius:6px 
  }

  .grid > div.even { 
    background:#ffdddd 
  }
  
  </style>
  