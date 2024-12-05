<template>
    <div class="catalog">
      <div class="filters">
        <input
          type="text"
          v-model="searchQuery"
          placeholder="Buscar por nombre"
        />
        <select v-model="selectedCategory">
          <option value="">Todas las categorías</option>
          <option v-for="category in categories" :key="category" :value="category">
            {{ category }}
          </option>
        </select>
      </div>
      <div class="product-list">
        <div v-for="product in filteredProducts" :key="product.id" class="product">
          <div class="image-container">
            <img :src="product.img" alt="Imagen del producto">
          </div>
          <h3>{{ product.name }}</h3>
          <p>{{ product.description }}</p>
          <p>Precio: ${{ product.price }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import ballena_iluminacion from './../assets/img/ballena_iluminacion.png';
  import medusa_iluminacion from './../assets/img/medusa_iluminacion.jpg';
  import faro from './../assets/img/faro.jpg';
  import iman_barcelona from './../assets/img/iman_barcelona.png';
  import skyline_barcelona from './../assets/img/skyline_barcelona.jpg';
  
  export default {
    data() {
      return {
        searchQuery: '',
        selectedCategory: '',
        products: [
          { id: 1, name: 'Figura de Madera 1', description: 'Descripción 1', category: 'Imanes', price: 20, img: faro  },
          { id: 2, name: 'Figura de Madera 2', description: 'Descripción 2', category: 'Souvenirs', price: 15, img: iman_barcelona  },
          { id: 3, name: 'Figura de Madera 3', description: 'Descripción 3', category: 'Skyline', price: 15, img: skyline_barcelona  },
          { id: 4, name: 'Figura de Madera 4', description: 'Descripción 4', category: 'Trofeos', price: 15, img: ballena_iluminacion },
          { id: 5, name: 'Lámpara Medusa', description: 'Descripción 5', category: 'Iluminacion', price: 15, img: medusa_iluminacion },
          { id: 5, name: 'Lámpara Medusa', description: 'Descripción 5', category: 'Iluminacion', price: 15, img: medusa_iluminacion },
          { id: 5, name: 'Lámpara Medusa', description: 'Descripción 5', category: 'Iluminacion', price: 15, img: medusa_iluminacion },
          { id: 5, name: 'Lámpara Medusa', description: 'Descripción 5', category: 'Iluminacion', price: 15, img: medusa_iluminacion },
        ],
      };
    },
    computed: {
      categories() {
        return [...new Set(this.products.map(product => product.category))];
      },
      filteredProducts() {
        return this.products.filter(product => {
          return (
            (this.selectedCategory === '' || product.category === this.selectedCategory) &&
            product.name.toLowerCase().includes(this.searchQuery.toLowerCase())
          );
        });
      },
    },
  };
  </script>
  
  <style scoped>
  .catalog {
    display: flex;
    flex-direction: column;
    padding: 1rem;
  }
  
  .filters {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1rem;
  }
  
  .product-list {
    justify-content: center;
  display: flex;
  flex-wrap: wrap;
  gap: 1rem; /* Espacio entre los productos */
}


  .product {
    border: 1px solid #ccc;
    padding: 1rem;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    width: 400px;
    height: 400px;
    background: rgb(236, 236, 236);
    box-shadow: rgba(0, 0, 0, 0.4) 0px 2px 4px, rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, rgba(0, 0, 0, 0.2) 0px -3px 0px inset;
  }
  
  .image-container {
    width: 100%;
    height: 200px; /* Ajusta esto según tus necesidades */
    overflow: hidden;
    border-radius: 5px;
    margin-bottom: 1rem;
  }
  
  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Asegura que la imagen mantenga una apariencia consistente */
  }
  </style>
  