<template>
  <div class="row">
    <div class="col-lg-3 p-2" v-for="product in products" :key="product.id">
      <div class="card " >
        <img :src="product.image" class="card-img-top" alt="..." />
        <div class="card-body">
          <h5 class="card-title">{{ product.name }}</h5>
          <p>{{ product.brand }}</p>
          <RouterLink class="btn btn-primary" :to="'/'+ product.id">Product Detail</RouterLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductsList",
  props: ['products'],
};
</script>
