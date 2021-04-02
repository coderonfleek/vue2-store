<template>
  <div class="home container">
    <div class="row">
      <div class="col-md-9 pt-5">

       <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-3 row-cols-xl-5">
          <Product v-for="product in products" :product="product" :key="product.id" />
       </div>
        
      </div>
      <div class="col-md-3 pt-5">
        <!-- <SideNav /> -->
        <Cart />
      </div>
      
    </div>
  </div>
</template>

<script>
// import SideNav from "../components/SideNav.vue";
import Product from "../components/Product.vue";
import Cart from "../components/Cart.vue";

import {mapState} from "vuex";

export default {
  name: 'Home',
  components: {
    //SideNav,
    Product,
    Cart
  },
  data(){
    return {
      
    }
  },
  computed : {
    ...mapState({
      products : state => state.products,
      cart : state => state.cart
    })
  }
  
}
</script>
