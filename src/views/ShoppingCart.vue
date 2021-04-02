<template>
  <div class="home container">
    <div class="row">
      <div class="col-md-8 pt-5">

       <CartItem v-for="product in cart" :product="product" :key="product.id" />
        
      </div>
      <div class="col-md-4 pt-5">
        <!-- <SideNav /> -->
        <Cart />
      </div>
      
    </div>
  </div>
</template>

<script>
// import SideNav from "../components/SideNav.vue";
import CartItem from "../components/CartItem.vue";
import Cart from "../components/Cart.vue";
import {mapState} from "vuex";

export default {
  name: 'ShoppingCart',
  components: {
    //SideNav,
    CartItem,
    Cart
  },
  data(){
    return {
     
    }
  },
  computed : {
    ...mapState({
        cart : state => state.cart
    }),
  }
}
</script>
