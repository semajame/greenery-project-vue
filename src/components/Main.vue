<template>
  <div class="hero">
    <header>
      <div class="left__header">
        <router-link
          :to="links.path"
          class="router__link"
          v-for="links in navContent"
          :key="links.path"
        >
          {{ links.component }}
        </router-link>
      </div>
      <div class="logo__header">
        <router-link :to="{ name: 'home' }" class="router__link"
          ><img
            src="https://assets.website-files.com/64ed01cfd959df99c0368448/64f0511f8895504cb56aef87_The%20Greenery%20(2).svg"
            alt="Logo"
          />
        </router-link>
      </div>
      <div class="right__header">
        <router-link :to="{ name: 'contacts' }" class="router__link"
          >Contacts</router-link
        >
        <button class="cart__button">
          <img :src="cartIcon" alt="Cart Icon" class="cart" />
        </button>
      </div>
    </header>
    <div class="main__hero">
      <div class="hero__left">
        <h1>
          {{ heroHeader }}
          <span class="span__color__black">{{ spanBlack }}</span>
        </h1>

        <p>
          {{ heroPara }}
        </p>
      </div>

      <div class="button__container">
        <button class="discover__button">{{ discoverButton }}</button>
        <button class="scroll__more">
          {{ scrollButton }} <img :src="arrowDown" alt="Arrow Down" />
        </button>
      </div>
    </div>
  </div>
  <Company />
  <Shop />
  <Quality />
  <Footer />
</template>

<script>
import Company from "./Company.vue";
import Shop from "./Shop.vue";
import Quality from "./Quality.vue";
import Footer from "./Footer.vue";

export default {
  data() {
    return {
      cartIcon: require("@/assets/cart-icon.svg"),
      arrowDown: require("@/assets/arrow-down-solid.svg"),
      heroHeader: "Finest selection of",
      heroPara:
        " We believe that green living starts from within. Step into a world of vibrant foliage and unlock the secrets of creating your own lush indoor garden.",
      spanBlack: "plants",
      discoverButton: "Discover our plants",
      scrollButton: "Scroll for more",

      navContent: [
        {
          path: "/",
          name: "home",
          component: "Home",
        },

        {
          path: "/explore",
          name: "explore",
          component: "Explore",
        },
        {
          path: "/blog",
          name: "blog",
          component: "Blog",
        },
      ],
    };
  },

  components: {
    Company,
    Shop,
    Quality,
    Footer,
  },
};
</script>

<style></style>
