<template>
<div class="rating">{{ stars }}</div>
</template>

<script>
// Componente para mostrar una calificación en estrellas basada en un valor numérico
export default {
  name:'Rating',
  props:{ value: Number },
  computed:{
    stars(){
      const v = Math.round(this.value ?? 0);
      return '★'.repeat(v) + '☆'.repeat(5 - v);
    }
  }
}
</script>

<style scoped>

.rating { 
  font-size:1.4rem 
  }
  
  </style>
