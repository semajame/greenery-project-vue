<template>
  <NavBar />

  <main class="explore__container">
    <h1>{{ exploreHeader }}</h1>
  </main>

  <section class="explore__button__container">
    <button
      v-for="button in buttons"
      :key="button.category"
      :class="{ active: button.isActive }"
      @click="activeButton(button), filterPlants(button.category)"
      :data-name="button.buttonName"
    >
      {{ button.buttonName }}
    </button>
  </section>

  <section class="explore__plants__container">
    <div class="shop__container">
      <div
        class="product__container"
        :data-category="items.category"
        v-for="items in filteredPlants"
        :key="items.id"
      >
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
          <div class="product__quantity__cart">
            <input
              type="number"
              value="1"
              class="quantity"
              @input="onlyNumber"
            />

            <button class="add__to__cart">Add to Cart</button>
          </div>
        </div>
      </div>
    </div>
  </section>
  <Footer />
</template>

<script>
import NavBar from "../components/NavBar.vue";
import Footer from "../components/Footer.vue";
export default {
  data() {
    return {
      exploreHeader: "Explore our green world",
      isActive: false,

      buttons: [
        {
          category: "All",
          buttonName: "All",
        },
        {
          category: "Flowering Plants",
          buttonName: "Flowering Plants",
        },
        {
          category: "Succulents",
          buttonName: "Succulents",
        },
        {
          category: "Air Purifiers",
          buttonName: "Air Purifiers",
        },
        {
          category: "Low-Maintenance",
          buttonName: "Low-Maintenance",
        },
        {
          category: "Indoor Foliage",
          buttonName: "Indoor Foliage",
        },
      ],

      plants: [
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1e641d50ae58a7cccc98_feey-dTLeHGu9FAw-unsplash.jpg",
          name: "Jesse",
          price: "$ 18.00 USD",
          id: "1",
          category: ["Flowering Plants", "Low Maintenance"],
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1d726de45ea0e0551508_feey-8nONCr6eTeg-unsplash.jpg",
          name: "Winson",
          price: "$ 24.00 USD",
          id: "2",
          category: ["Succulents", "Low-Maintenance"],
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef1cfc570c8023bd5b3e05_feey-shAA_rxG2Yc-unsplash.jpg",
          name: "Venus",
          price: "$ 30.00 USD",
          id: "3",
          category: ["Flowering Plants", "Succulents"],
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef0d32c3b6732ca16db980_feey-bwsTJMnhcwE-unsplash.jpg",
          name: "Lineo",
          price: "$ 18.00 USD",
          id: "4",
          category: ["Flowering Plants", "Air Purifiers", "Indoor Foliage"],
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef0ce17576e9baae98663f_feey-eeOOH0dk3XQ-unsplash.jpg",
          name: "Mark",
          price: "$ 30.00 USD",
          id: "5",
          category: ["Succulents", "Air Purifiers", "Indoor Foliage"],
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef0cc296e00eaf5ca2cab8_feey-cLaaxa4DSnc-unsplash.jpg",
          name: "Fushion",
          price: "$ 24.00 USD",
          id: "6",
          category: ["Low-Maintenance", "Indoor Foliage"],
        },
        {
          image:
            "https://assets.website-files.com/64ed01d0d959df99c03684cc/64ef0c921b293c2901ab0265_feey-dAA2Q_eFb84-unsplash.jpg",
          name: "Lucky",
          price: "$ 18.00 USD",
          id: "7",
          category: ["Air Purifiers"],
        },
      ],

      selectedCategory: "All",
    };
  },

  methods: {
    activeButton(clickedButton) {
      this.buttons.forEach((button) => {
        if (button !== clickedButton) {
          button.isActive = false;
        }
      });

      clickedButton.isActive = !clickedButton.isActive;
    },

    filterPlants(category) {
      this.selectedCategory = category;
    },
  },

  computed: {
    filteredPlants() {
      if (this.selectedCategory === "All") {
        return this.plants;
      } else {
        return this.plants.filter((items) =>
          items.category.includes(this.selectedCategory)
        );
      }
    },

    onlyNumber() {
      const input = document.querySelectorAll(".quantity");

      input.forEach((quantity) => {
        quantity.addEventListener("input", () => {
          const numbersOnly = /^\d+$/;

          if (!numbersOnly.test(quantity.value)) {
            quantity.value = "";
          }
        });
      });
    },
  },

  components: {
    NavBar,
    Footer,
  },
};
</script>

<style></style>
