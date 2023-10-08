<template>
  <NavBar />

  <main class="cart__main">
    <h1>Cart</h1>
  </main>

  <section class="cart__container">
    <div
      class="cart__product"
      v-for="(product, index) in cartProducts"
      :key="index"
    >
      <div>
        <div class="cart__product__image">
          <img :src="product.imageSrc" alt="" />
        </div>
        <div class="cart__product__info">
          <span class="cart__product__name">{{ product.name }}</span>
          <span class="cart__price">{{ product.price }}</span>
          <button class="cart__remove__button" @click="removeCart(index)">
            Remove
          </button>
        </div>
      </div>

      <div class="input__container">
        <input type="number" class="quantity" v-model="product.quantity" />
      </div>
    </div>

    <div class="cart__total__container">
      <div class="sub__total">
        <span>Subtotal</span>

        <span class="total">$24.00 USD</span>
      </div>
    </div>
  </section>
</template>

<script>
import NavBar from "../components/NavBar.vue";
export default {
  data() {
    return {
      cartProducts: [
        {
          name: "Winson",
          price: "$24.00 USD",
          imageSrc:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1e641d50ae58a7cccc98_feey-dTLeHGu9FAw-unsplash.jpg",
          quantity: 1, // You can set the initial quantity here
        },
        {
          name: "asd",
          price: "$25.00 USD",
          imageSrc:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1e641d50ae58a7cccc98_feey-dTLeHGu9FAw-unsplash.jpg",
          quantity: 1, // You can set the initial quantity here
        },
        // Add more products as needed
      ],
    };
  },

  methods: {
    removeCart(index) {
      // Remove the product at the specified index from the cart
      this.cartProducts.splice(index, 1);
    },
  },

  components: {
    NavBar,
  },
};
</script>

<style></style>
