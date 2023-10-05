<template>
  <header class="home__header">
    <div class="left__header">
      <router-link
        :to="links.path"
        class="router__link span__color__black"
        v-for="links in navContent"
        :key="links.path"
      >
        {{ links.component }}
      </router-link>
    </div>
    <div class="logo__header header__logo">
      <router-link
        :to="{ name: 'home' }"
        class="router__link span__color__black"
        ><img
          src="https://assets.website-files.com/64ed01cfd959df99c0368448/64f0511f8895504cb56aef87_The%20Greenery%20(2).svg"
          alt="Logo"
        />
      </router-link>
    </div>
    <div class="right__header">
      <router-link
        :to="{ name: 'contacts' }"
        class="router__link span__color__black"
        >Contacts</router-link
      >
      <button class="cart__button">
        <img :src="cartIcon" alt="Cart Icon" class="cart__header" />
      </button>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      cartIcon: require("@/assets/cart-icon.svg"),

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
};
</script>
