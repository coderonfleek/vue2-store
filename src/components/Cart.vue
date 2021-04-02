<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title">Your Cart</h5>
            <p v-if="cart.length == 0">
                Your Cart is Empty
            </p>
        </div>
        <ul class="list-group list-group-flush">
            <li v-for="item in cart" :key="item.id" class="list-group-item d-flex justify-content-between align-items-center">
                {{item.name}}
                <span class="badge badge-primary badge-pill">{{item.quantity}}</span>
            </li>
            <li class="list-group-item d-flex justify-content-between align-items-center">
                Price <b>${{totalPrice}}</b>
            </li>
        </ul>
        
        <div class="card-body">
            <router-link to="/shop" class="btn btn-primary btn-block">Checkout</router-link>
        </div>
    </div>
</template>

<script>
import {mapState} from "vuex";

export default {
    computed : {
        ...mapState({
            cart : state => state.cart
        }),
        totalPrice(){
            return this.cart.reduce((total, next) => {
                return total + (next.quantity * next.price)
            }, 0)
        }
    }
}
</script>