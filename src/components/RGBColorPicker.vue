<template>
    <div class="rgb">
      <SingleColorPicker color="r" v-model="rValue" />
      <SingleColorPicker color="g" v-model="gValue" />
      <SingleColorPicker color="b" v-model="bValue" />
      <div class="result">
        <div class="square" :style="{ backgroundColor: rgb }"></div>
        <span>{{ rgb }}</span>
      </div>
    </div>
  </template>
  
  <script>
  import SingleColorPicker from './SingleColorPicker.vue'
  export default {
    name:'RGBColorPicker',
    components:{ SingleColorPicker },
    data(){ return { rValue: 255, gValue: 0, bValue: 0 } },
    computed:{ rgb(){ return `rgb(${this.rValue}, ${this.gValue}, ${this.bValue})`; } }
  }
  </script>
  
  <style scoped>
  .rgb{ display:grid; gap:10px; max-width:360px }
  .result{ display:flex; align-items:center; gap:10px }
  .square{ width:60px; height:40px; border:1px solid #ccc; border-radius:6px }
  </style>
  