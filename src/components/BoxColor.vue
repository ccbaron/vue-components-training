<template>
    <div class="box" :style="styleObj">
      <p>{{ rgbText }}</p>
      <p>{{ hexText }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'BoxColor',
    props: { r: Number, g: Number, b: Number },
    computed: {
      rgbText() { return `rgb(${this.r}, ${this.g}, ${this.b})`; },
      hexText() {
        const toHex = (v) => v.toString(16).padStart(2, '0');
        return `#${toHex(this.r)}${toHex(this.g)}${toHex(this.b)}`.toUpperCase();
      },
      styleObj() {
        const luminance = (0.299*this.r + 0.587*this.g + 0.114*this.b) / 255;
        const color = luminance > 0.6 ? '#000' : '#fff'; // contraste automático (bonus)
        return { backgroundColor: this.rgbText, color, padding: '20px', border: '1px solid #ccc', textAlign: 'center' };
      }
    }
  }
  </script>
