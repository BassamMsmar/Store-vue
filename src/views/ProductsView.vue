<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-lg-3">
        <FilterProducts @brands-updated="updateProducts" />
      </div>
      <div class="col-lg-9 ">
        <ProductsList :products="filterProducts"/>
      </div>
    </div>
  </div>
</template>

<script>
import FilterProducts from "../components/FilterProducts.vue";
import ProductsList from "../components/ProductsList.vue";
import { products } from '@/temp-data';


export default {
  name: "ProdcutsPage",
  components: {
    ProductsList,
    FilterProducts
  },
  data() {
    return {
      products:products,
      filterProducts:products
    }
  },
  methods: {
    updateProducts(selectedBrands){
      if (selectedBrands.length == 0){
        this.filterProducts = this.products
      }
      else {
        this.filterProducts = this.products.filter(product => selectedBrands.includes(product.brand))
      }
    }
  }
};
</script>
  
