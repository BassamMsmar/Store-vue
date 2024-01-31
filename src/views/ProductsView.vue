<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-lg-3">
        <Filter />
      </div>
      <div class="col-lg-9 ">
        <ProductsList :products="products"/>
      </div>
    </div>
  </div>
</template>

<script>
import Filter from "../components/FilterProducts.vue";
import ProductsList from "../components/ProductsList.vue";
import { products } from '@/temp-data';


export default {
  name: "ProdcutsPage",
  components: {
    Filter,
    ProductsList
  },
  data() {
    return {
      products:products
      
    }
  }
};
</script>
  
