<template>
    <form class="form" @submit.prevent="submit">
      <label>Email
        <input type="email" v-model="email" @input="validateEmail" :class="{ invalid: emailTouched && !emailValid }"/>
      </label>
  
      <label>Password
        <input type="password" v-model="password" @input="checkStrength" :class="{ weak: strength==='weak', medium: strength==='medium', strong: strength==='strong' }"/>
        <small>Strength: {{ strength }}</small>
      </label>
  
      <label>Nationality
        <select v-model="nat">
          <option value="en">en</option>
          <option value="de">de</option>
          <option value="fr">fr</option>
        </select>
      </label>
  
      <button type="submit">Sign up</button>
  
      <div class="result" v-if="submitted">
        <p>{{ greeting }}</p>
        <p>Your email address is: {{ email }}</p>
      </div>
    </form>
  </template>
  
  <script>
  // Componente para una página de registro con validación de email, verificación de fuerza de contraseña y saludo según nacionalidad
  export default {
    name:'SignupPage',
    data(){
      return { email:'', emailValid:false, emailTouched:false, password:'', strength:'weak', nat:'en', submitted:false }
    },
    computed:{
      greeting(){
        const g = { en:'Hello', de:'Hallo', fr:'Bonjour' }[this.nat] || 'Hello';
        return `${g}`;
      }
    },
    methods:{
      validateEmail(){
        this.emailTouched = true;
        this.emailValid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.email);
      },
      checkStrength(){
        const p = this.password;
        const score = [/[a-z]/.test(p), /[A-Z]/.test(p), /\d/.test(p), /[^A-Za-z0-9]/.test(p), p.length>=8].filter(Boolean).length;
        this.strength = score >=4 ? 'strong' : score>=3 ? 'medium' : 'weak';
      },
      submit(){ this.submitted=true; }
    }
  }
  </script>
  
  <style scoped>

  .form { 
    display:grid; 
    gap:12px; 
    max-width:360px 
  }

  input, select { 
    padding:8px; 
    border:1px solid #ccc; 
    border-radius:6px 
  }

  input.invalid { 
    border-color:#ef4444; 
    background:#fee2e2 
  }

  input.weak { 
    border-color:#ef4444 
  }

  input.medium { 
    border-color:#f59e0b 
  }

  input.strong { 
    border-color:#10b981 
  }

  .result { 
    margin-top:10px; 
    padding:10px; 
    border:1px dashed #bbb; 
    border-radius:6px 
  }
  </style>
  