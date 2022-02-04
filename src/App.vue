<template>
<div class="container">
  <button type="button" class="btn btn-primary mt-3">
    Cart <span class="badge badge-light">{{ cart.length }}</span>
  </button>  <h1 class="text-center my-3">Shopping Cart</h1>
  <div class="row">
        <div class="col-lg-6 col-md-8 " v-for="product in products" :key="product.productId">
          <Product @add-to-cart="addToCart(product)" :product="product" :isInCart="isInCart(product)"></Product>
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
      cart:[]
    }
  },
  methods:{
    addToCart(product){
        this.cart.push(product)
    },
    isInCart(product){
      const item = this.cart.find(item => item.id === product.id)
      if(item) {
        return true
      }
      return false
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
