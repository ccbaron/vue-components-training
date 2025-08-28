<template><button @click="inc" :style="{ backgroundColor: currentColor }">{{ count }} Likes</button></template>
<script>
export default {
  name:'LikeButton',
  data(){ return { count:0, i:0, colors:['purple','blue','green','yellow','orange','red'] } },
  computed:{ currentColor(){ return this.colors[this.i % this.colors.length]; } },
  methods:{ inc(){ this.count++; this.i++; } }
}
</script>
<style scoped>button{ border:none; padding:10px 16px; color:#fff; border-radius:8px; cursor:pointer }</style>
