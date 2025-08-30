<template>
<img :src="isClicked ? imgClicked : img" @click="toggle" alt="" />
</template>

<script>
// Componente para mostrar una imagen que cambia al hacer clic
export default {
  name:'ClickablePicture',
  props:{ img:String, imgClicked:String },
  data(){ return { isClicked:false } },
  methods:{ toggle(){ this.isClicked=!this.isClicked } }
}
</script>

<style scoped>
img { 
  width:180px; 
  cursor:pointer; 
  border-radius:8px 
  }
  </style>
