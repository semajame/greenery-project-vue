<template>
  <section>
    <div class="shop__header">
      <h2>{{ shopHeader }}</h2>
      <router-link
        :to="{ name: 'explore' }"
        class="router__link span__color__black"
        >View all products</router-link
      >
    </div>
    <div class="shop__container">
      <div class="product__container" v-for="items in plants" :key="items.id">
        <div class="product__image">
          <img
            :src="items.image"
            loading="lazy"
            alt="Product Name"
            class="image-cover hover"
          />
        </div>

        <div class="product__footer">
          <div class="product__footer__flex">
            <h3 class="product__name">{{ items.name }}</h3>

            <button class="product__arrow__button">
              <img
                src="https://assets.website-files.com/64ed01cfd959df99c0368448/64ef122c8a3b67f03dbd9175_arrow-down-right.svg"
                loading="lazy"
                alt="Arrow Image"
                class="arrow__image"
              />
            </button>
          </div>
          <span class="product__price"> {{ items.price }} </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      shopHeader: "Explore a world of green possibilities",
      plants: [
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1e641d50ae58a7cccc98_feey-dTLeHGu9FAw-unsplash.jpg",
          name: "Jesse",
          price: "$ 18.00 USD",
          id: "1",
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1d726de45ea0e0551508_feey-8nONCr6eTeg-unsplash.jpg",
          name: "Winson",
          price: "$ 24.00 USD",
          id: "2",
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1cfc570c8023bd5b3e05_feey-shAA_rxG2Yc-unsplash.jpg",
          name: "Venus",
          price: "$ 30.00 USD",
          id: "3",
        },
      ],
    };
  },
};
</script>

<style></style>
