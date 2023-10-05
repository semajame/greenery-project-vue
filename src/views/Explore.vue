<template>
  <NavBar />

  <main class="explore__container">
    <h1>{{ exploreHeader }}</h1>
  </main>

  <div class="explore__button__container">
    <button v-for="button in buttons" :key="button.category">
      {{ button.category }}
    </button>
  </div>
</template>

<script>
import NavBar from "../components/NavBar.vue";
export default {
  data() {
    return {
      exploreHeader: "Explore our green world",

      buttons: [
        {
          category: "All",
        },
        {
          category: "Flowering Plants",
        },
        {
          category: "Succulents",
        },
        {
          category: "Air Purifiers",
        },
        {
          category: "Low-Maintenance",
        },
        {
          category: "Indoor Foliage",
        },
      ],
    };
  },

  methods: {},

  components: {
    NavBar,
  },
};
</script>

<style></style>
