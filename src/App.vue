<script setup>
import IdCard from './components/IdCard.vue';
import Random from './components/Random.vue'; // Importamos el nuevo componente Random
</script>

<template>
  <div id="app">
    <h1>Creación de componentes con Vue</h1>
    <p>Crea a continuación todos los componentes del ejercicio.</p>

    <!-- Ejemplo del componente IdCard -->
    <IdCard
      lastName="Doe"
      firstName="John"
      gender="male"
      :height="178"
      :birth="new Date('1992-07-14')"
      picture="https://randomuser.me/api/portraits/men/44.jpg"
    />
    <IdCard
      lastName="Delores"
      firstName="Obrien"
      gender="female"
      :height="172"
      :birth="new Date('1988-05-11')"
      picture="https://randomuser.me/api/portraits/women/44.jpg"
    />

    <!-- Ejemplo del componente Random -->
    <Random :min="1" :max="6" />
    <Random :min="1" :max="100" />
  </div>
</template>

<style scoped>
/* Add any global styles here */
</style>
