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
    <div class="shop_container"></div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      shopHeader: "Explore a world of green possibilities",
    };
  },
};
</script>

<style></style>
