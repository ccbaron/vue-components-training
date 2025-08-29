<template>
  <!-- Componente para mostrar una tarjeta de identificación -->
  <div class="id-card">
    <!-- Imagen del perfil -->
    <img :src="picture" alt="Profile Picture" />
    <div>
      <!-- Información del usuario -->
      <p><strong>Last Name:</strong> {{ lastName }}</p>
      <p><strong>First Name:</strong> {{ firstName }}</p>
      <p><strong>Gender:</strong> {{ gender }}</p>
      <p><strong>Height:</strong> {{ height }}cm</p>
      <p><strong>Birth:</strong> {{ new Date(birth).toDateString() }}</p>
    </div>
  </div>
</template>

<script>
// Componente para mostrar una tarjeta de identificación
export default {
  name: 'IdCard',
  props: {
    // Propiedades que recibe el componente
    lastName: String, // Apellido
    firstName: String, // Nombre
    gender: String, // Género
    height: Number, // Altura en cm
    birth: Date, // Fecha de nacimiento
    picture: String, // URL de la imagen del perfil
  },
};
</script>

<style scoped>

/* Estilos para el componente de tarjeta de identificación */
.id-card {
  display: flex;
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px 0;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
.id-card img {
  max-width: 100px;
  margin-right: 15px;
  border-radius: 5px;
}
.id-card div {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
