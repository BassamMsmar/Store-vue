<template>
  <div class="container">
    <div class="row">
      <div class="col-lg-6">
        <img :src="product.image"/>
      </div>

      <div class="col-lg-6 pt-5">
        <h1>{{ product.name }}</h1>
        <p>{{ product.price }}</p>
        <p>{{ product.brand }}</p>

        <form class="row mt-4">
          <div class="col-lg-6">
            <input type="number" class="form-control" placeholder="1" />
          </div>
          <div class="col-lg-6">
            <button class="btn btn-primary d-block">Add to Cart</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { products } from "@/temp-data";
export default {
  name: "ProdcutDetailPage",
  data() {
    return {
      product: products.find(product => product.id == this.$route.params.productId)
      ,
    }
  }
};
</script>
