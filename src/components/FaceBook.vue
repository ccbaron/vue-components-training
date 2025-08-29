<template>
    <div class="fb">
      <div class="filters">
        <button
          v-for="c in countries" :key="c"
          :class="{ active: c===activeCountry }"
          @click="toggleCountry(c)"
        >{{ c }}</button>
        <button @click="toggleCountry(null)">Reset</button>
      </div>
  
      <div class="cards">
        <div
          v-for="p in profiles" :key="p.firstName + p.lastName"
          class="card"
          :class="{ highlight: activeCountry && p.country===activeCountry }"
        >
          <img :src="p.img" alt="" />
          <div>
            <p><strong>First name:</strong> {{ p.firstName }}</p>
            <p><strong>Last name:</strong> {{ p.lastName }}</p>
            <p><strong>Country:</strong> {{ p.country }}</p>
            <p><strong>Type:</strong> {{ p.isStudent ? 'Student' : 'Teacher' }}</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  const sample = [
    { firstName:'John', lastName:'Doe', country:'USA', isStudent:true, img:'https://randomuser.me/api/portraits/men/12.jpg' },
    { firstName:'Obrien', lastName:'Delores', country:'Germany', isStudent:false, img:'https://randomuser.me/api/portraits/women/34.jpg' },
    { firstName:'Alex', lastName:'Müller', country:'Germany', isStudent:true, img:'https://randomuser.me/api/portraits/men/44.jpg' },
    { firstName:'Camille', lastName:'Durand', country:'France', isStudent:false, img:'https://randomuser.me/api/portraits/women/64.jpg' },
  ];
  export default {
    name:'FaceBook',
    data(){ return { profiles: sample, activeCountry: null } },
    computed:{
      countries(){ return [...new Set(this.profiles.map(p=>p.country))]; }
    },
    methods:{
      toggleCountry(c){ this.activeCountry = c; }
    }
  }
  </script>
  
  <style scoped>
  .filters{ display:flex; gap:8px; margin-bottom:10px; flex-wrap:wrap }
  .filters button.active{ background:#3b82f6; color:#fff }
  .cards{ display:grid; grid-template-columns: repeat(auto-fill, minmax(260px,1fr)); gap:10px }
  .card{ display:flex; gap:12px; border:1px solid #ddd; border-radius:8px; padding:10px; background:#fff }
  .card.highlight{ background:#dbeafe; border-color:#93c5fd }
  .card img{ width:80px; height:80px; border-radius:6px; object-fit:cover }
  </style>
  