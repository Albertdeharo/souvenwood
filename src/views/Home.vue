<template>
  <div>
    <Banner />
    <Gallery />
    <Catalog />
  </div>
</template>

<script>
import Banner from '../components/Banner.vue';
import Gallery from '../components/Gallery.vue';
import Catalog from '../components/Catalog.vue';

export default {
  components: {
    Banner,
    Catalog,
    Gallery
  }
};
</script>
