<template>
<div class="container">
  <div class="row">
    <div class="col-md-7">
      <div class="row">
        <div class="col-md-6" v-for="product in products" :key="product.productId">
          <Product>{{ product}}</Product>
        </div>
      </div>
      <Product/>
      <Product/>
    </div>
    <div class="col-md-5"></div>
  </div>
</div>
</template>

<script>
import products from './products.json'
import Product from "@/components/Product";

export default {
  name: 'App',
  components:{
    Product
  },
  data(){
    return{
      products
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
