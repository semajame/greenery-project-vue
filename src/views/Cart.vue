<template>
  <NavBar />

  <main class="cart__main">
    <h1>Cart</h1>
  </main>

  <section class="cart__container">
    <div class="cart__product">
      <div>
        <div class="cart__product__image">
          <img
            src="https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1e641d50ae58a7cccc98_feey-dTLeHGu9FAw-unsplash.jpg"
            alt=""
          />
        </div>
        <div class="cart__product__info">
          <span class="cart__product__name"> Winson</span>
          <span class="cart__price">$24.00 USD</span>
          <button class="cart__remove__button">Remove</button>
        </div>
      </div>
      <div class="input__container">
        <input type="number" class="quantity" />
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
    return {};
  },

  components: {
    NavBar,
  },
};
</script>

<style></style>
