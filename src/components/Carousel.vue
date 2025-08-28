<template>
    <div class="carousel">
      <button @click="prev">‹</button>
      <img :src="images[index]" alt="" />
      <button @click="next">›</button>
    </div>
  </template>
  
  <script>
  export default {
    name:'Carousel',
    props:{ images:{ type:Array, required:true } },
    data(){ return { index:0 } },
    methods:{
      prev(){ this.index = (this.index - 1 + this.images.length) % this.images.length; },
      next(){ this.index = (this.index + 1) % this.images.length; }
    }
  }
  </script>
  
  <style scoped>
  .carousel{ display:flex; align-items:center; gap:10px }
  .carousel img{ width:260px; height:160px; object-fit:cover; border-radius:8px }
  button{ padding:8px 10px }
  </style>
  