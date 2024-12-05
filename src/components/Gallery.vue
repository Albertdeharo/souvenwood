<template>
    <section class="gallery">
      <h2>Nuestra Galería de Productos</h2>
      <div class="gallery-grid">
        <div v-for="(product, index) in products" :key="index" class="gallery-item">
          <img :src="product.image" :alt="product.name" class="product-image" />
          <div class="product-info">
            <h3 class="product-name">{{ product.name }}</h3>
            <p class="product-price">${{ product.price.toFixed(2) }}</p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "Gallery",
    data() {
      return {
        products: [
          { name: "Figura de madera 1", image: "https://via.placeholder.com/300x300?text=Producto+1", price: 49.99 },
          { name: "Figura de madera 2", image: "https://via.placeholder.com/300x300?text=Producto+2", price: 59.99 },
          { name: "Figura de madera 3", image: "https://via.placeholder.com/300x300?text=Producto+3", price: 39.99 },
          // Agrega más productos según sea necesario
        ]
      };
    }
  };
  </script>
  
  <style scoped lang="scss">
  .gallery {
    padding: 2rem;
    text-align: center;
    background-color: #f9f9f9;
  }
  
  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
  }
  
  .gallery-item {
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }
  
  .product-image {
    width: 100%;
    height: auto;
    display: block;
  }
  
  .product-info {
    padding: 1rem;
    text-align: left;
  }
  
  .product-name {
    font-size: 1.1rem;
    margin-bottom: 0.5rem;
  }
  
  .product-price {
    font-size: 1rem;
    color: #2ecc71;
  }
  </style>
  