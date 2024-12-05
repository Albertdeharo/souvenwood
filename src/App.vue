<template>
  <div class="app-container">
    <Navbar />
    <main class="main-content">
      <Home />
    </main>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
import Home from './views/Home.vue';

export default {
  components: {
    Navbar,
    Footer,
    Home,
  },
};
</script>

<style>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100dvh;
}

.main-content {
  flex: 1; /* Esto hace que el contenido principal ocupe el espacio disponible */
}
</style>
