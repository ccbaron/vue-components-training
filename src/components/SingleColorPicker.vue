<template>
    <div class="row">
      <label>{{ label }}</label>
      <input type="number" min="0" max="255" :value="modelValue" @input="$emit('update:modelValue', Number($event.target.value))" />
      <div class="preview" :style="{ backgroundColor: previewColor }"></div>
    </div>
  </template>
  
  <script>
  export default {
    name:'SingleColorPicker',
    props:{ color:{ type:String, required:true }, modelValue:{ type:Number, required:true } },
    computed:{
      label(){ return this.color.toUpperCase() + ':'; },
      previewColor(){
        const r = this.color==='r' ? this.modelValue : 0;
        const g = this.color==='g' ? this.modelValue : 0;
        const b = this.color==='b' ? this.modelValue : 0;
        return `rgb(${r}, ${g}, ${b})`;
      }
    }
  }
  </script>
  
  <style scoped>
  .row{ display:flex; align-items:center; gap:10px }
  .preview{ width:30px; height:20px; border:1px solid #ccc }
  </style>