<template>
<div class="container">
  <button type="button" class="btn btn-primary mt-3">
    Cart <span class="badge badge-light">{{ cart }}</span>
  </button>  <h1 class="text-center my-3">Shopping Cart</h1>
  <div class="row">
        <div class="col-lg-6 col-md-8 " v-for="product in products" :key="product.productId">
          <Product :product="product"></Product>
        </div>
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
      products,
      cart:0
    }
  },
  methods:{
    addToCart(product){
      console.log(product)

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
