<template><img :src="src" @click="roll" alt="dice" /></template>
<script>
// Componente para mostrar un dado que cambia su valor al hacer clic, con animación de lanzamiento
export default {
  name:'Dice',
  data(){ return { value: this.rand1to6(), rolling:false } },
  computed:{
    src(){
      if (this.rolling) return new URL('../assets/images/dice-empty.png', import.meta.url).href;
      return new URL(`../assets/images/dice${this.value}.png`, import.meta.url).href;
    }
  },
  methods:{
    rand1to6(){ return Math.floor(Math.random()*6)+1; },
    roll(){
      this.rolling=true;
      setTimeout(()=>{ this.value=this.rand1to6(); this.rolling=false; }, 1000);
    }
  }
}
</script>
<style scoped> 

img { 
  width:100px; 
  cursor:pointer 
  }
  </style>
