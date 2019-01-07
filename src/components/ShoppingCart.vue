<template>
  <div class="cart">
    <p class="cart-title">Shopping Cart</p>
    <p class="cart-empty" v-if="total == 0">your shopping cart is empty</p>
    <div class="items" v-else>
      <div class="item" v-for="item in items">
        <img :src="'/dist/' + item.image" class="item-image">
        <div class="item-details">
          <p class="item-title">{{item.title}}</p>
          <p class="item-price">
            <span>x{{item.qty}}</span>
            <span class="right">$ {{item.qty + item.price}}</span>
          </p>
        </div>
      </div>
    </div>
    <div class="cart-total">
      <span>total</span>
      <span class="right">$ {{total}}</span>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: []
    }
  },
  computed: {
    total (){
      return 0
    }
  }
}
</script>

<style>
  .cart {
    margin-left: 1em;
  }
  .cart-title {
    margin: 0.5em 0 0 0;
    font-weight: bold;
    text-transform: uppercase;
    text-align: center;
    padding: 0.75em;
    background: #35495E;
    color: #fff;
  }

  .cart-empty {
    text-align: center;
    margin: 4em 0 0 0;
    min-height: 300px;
  }
  .cart-total {
    background: #F1F1F1;
    margin: 0;
    padding: 0.75em;
  }

  .items {
    min-height: 300px;
  }

  .item {
    padding: 0.75em 0.5em;
    border-top: 1px solid #ddd;
  }

  .right {
    float: right;
  }

  .item-image {
    float: left;
    width: 20%;
  }
  .item-details {
    float: left;
    width: 80%;
    padding-left: 0.75em;
  }
  .item-title {
    margin: 0;
    font-weight: bold;
  }
  .item-price {
    margin: 0;
    font-size: 0.9em;
  }
</style>