<template>
  <div>
    <!-- Mostramos un número aleatorio entre min y max -->
    <p>Random value between {{ min }} and {{ max }} => {{ randomValue }}</p>
  </div>
</template>

<script>
// Componente para mostrar un número aleatorio entre dos valores dados (min y max)
export default {
  name: 'Random',
  props: {
    min: {
      type: Number,
      required: true,
    },
    max: {
      type: Number,
      required: true,
    },
  },
  computed: {
    // Calculamos un valor aleatorio entre min y max
    randomValue() {
      return Math.floor(Math.random() * (this.max - this.min + 1)) + this.min;
    },
  },
};
</script>

<style scoped>
/* Estilos opcionales para el componente Random */
</style>