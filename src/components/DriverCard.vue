<template>
    <div class="driver">
      <img :src="img" :alt="`Foto de ${name}`" />
      <div class="info">
        <h3>{{ name }}</h3>
        <p class="rate">{{ ratingStars }}</p>
        <p>{{ car.model }} — {{ car.licensePlate }}</p>
      </div>
    </div>
  </template>
  
  <script>
  // Componente para mostrar una tarjeta de conductor con su información y estilo personalizado
  export default {
    name:'DriverCard',
    props:{ name:String, rating:Number, img:String, car:{ type:Object, required:true } },
    computed:{
      ratingStars(){ const v=Math.round(this.rating??0); return '★'.repeat(v)+'☆'.repeat(5-v); }
    }
  }
  </script>
  
  <style scoped>
  .driver { 
    display:flex; 
    align-items:center; 
    gap: 24px; 
    background:#455eb5; 
    color:#fff; 
    padding:16px 28px; 
    border-radius:18px 
  }

  .driver img { 
    width:120px; 
    height:120px; 
    border-radius:50%; 
    object-fit:cover; 
    border:4px solid #fff4 
  }

  .rate { 
    margin: 0;
    font-size:1.2rem 
  }

  .info{
  display:flex;
  flex-direction:column;
  gap:8px;
  }
  </style>