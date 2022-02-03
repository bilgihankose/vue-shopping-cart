<template>
<div class="product-container mb-2 p-3">
  <img :src="imageURL" alt="product image" width="100px" height="300px">
  <div class="p-3">
    <h5 class="card-title">{{ product.brand}}</h5>
    <p>{{ product.name }}</p>
    <p >{{ product.priceText }}</p>
    <p class="text-muted">{{ product.categories }}</p>
    <a href="#" class="btn btn-primary">Add To Cart</a>
  </div>
</div>
</template>

<script>
export default {
  name: "Product",
  props:['product'],
  computed: {
   imageURL(){
     return this.product.imageS
   }
  }
}
</script>

<style scoped>
.product-container{
  display: flex;
  border: 1px solid #eee;
}
</style>