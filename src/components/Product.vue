<template>
<div class="d-flex product-container mb-2 p-3 border">
  <img :src="imageURL" alt="product image" width="100px" height="300px">
  <div class="p-3">
    <h5 class="card-title">{{ product.brand}}</h5>
    <p>{{ product.name }}</p>
    <p >{{ product.priceText }}</p>
    <p class="text-muted">{{ product.categories }}</p>
    <button class="btn btn-outline-primary add-to-card">Add To Cart</button>
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
.add-to-card{
  position: absolute;
  bottom: 25px;
  right: 30px;
}
</style>