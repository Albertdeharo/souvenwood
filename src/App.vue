<template>
  <div class="app-container">
    <Header />
    <main class="main-content">
      <Home />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Home from './views/Home.vue';

export default {
  components: {
    Header,
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
