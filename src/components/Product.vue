<template>
<div class="d-flex product-container mb-2 p-3 border">
  <img :src="imageURL" alt="product image" width="100px" height="300px">
  <div class="p-3">
    <h4 class="card-title text-primary">{{ product.brand}}</h4>
    <p>{{ product.name }}</p>
    <p class="text-muted">{{ product.categories }}</p>
    <h5 class="font-weight-bolder price-tag">{{ product.priceText }}</h5>
    <button @click="$emit('add-to-cart',product)" class="btn btn-outline-primary add-to-card">Add to cart</button>
  </div>
</div>
</template>

<script>
export default {
  name: "Product",
  props:['product', "isInCart"],
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
.price-tag{
  position: absolute;
  bottom: 60px;
  right: 30px;
}
.product-container:hover {
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
</style>