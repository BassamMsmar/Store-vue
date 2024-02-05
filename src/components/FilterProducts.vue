<template>
  <div class="container px-3">
    <h3>Filter Products</h3>
    <form>
      <div>
        <label for="brandFilter" class="form-label"> Filter By Brand</label>
        <div v-for="brand in brands" :key="brand.id" class="form-check">
          <input
            type="checkbox"
            :value="brand.id"
            :id="'brand-' + brand.id"
            class="form-check-input"
            v-model="selectedBrands"
          />

          <label :for="'brand-' + brand.id" class="form-label">
            {{ brand.name }}
          </label>
     
        </div>
      </div>
    </form>
  </div>
</template>

<script>

export default {
  name: "FilterProducts",
  data() {
    return {
      brands: [
        {id:1, name: "Apple"},
        {id:2, name: "Samsung"},
        {id:3, name: "Xiaomi"},
      ],
      selectedBrands:[]
    }
  },
  watch:{
    selectedBrands(){
      this.$emit('brands-updated', this.selectedBrands)
      
    }
  } 
};
</script>
