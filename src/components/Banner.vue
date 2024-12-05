<template>
  <section class="banner">
    <div class="banner-content">
      <h1>Bienvenido a SouvenWood</h1>
      <p>Decoraciones y souvenirs únicos hechos a mano</p>
      <button>Explorar Productos</button>
    </div>
  </section>
</template>

<script>
import banner_img from './../assets/img/banner.jpg';

export default {
  name: 'Banner',
};
</script>

<style scoped>
.banner {
  position: relative;
  width: 100%;
  height: 80dvh; /* Ajusta según tus necesidades */
  background-image: url('./../assets/img/banner.jpg'); /* Usar importación */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  text-align: center;
}

.banner-content {
  padding: 20px;
  background-color: rgba(0, 0, 0, 0.5); /* Fondo semitransparente */
  border-radius: 10px;
}

.banner h1 {
  margin-bottom: 10px;
}

.banner p {
  margin-bottom: 20px;
}

.banner button {
  padding: 10px 20px;
  background-color: #333;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.banner button:hover {
  background-color: #555;
}
</style>
