<template>
  <section class="quality__section">
    <div class="quality__container" v-for="items in quality" :key="items.id">
      <div class="quality__header__container">
        <span class="quality__number"> {{ items.qualNum }}</span>
        <h2 class="quality__header">{{ items.qualHeader }}</h2>
      </div>

      <p class="quality__paragraph">{{ items.qualPara }}</p>

      <hr />
    </div>

    <div class="learn__container">
      <router-link :to="{ name: 'contacts' }" class="learn__more">
        Learn More</router-link
      >
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      quality: [
        {
          qualNum: "01.",
          qualHeader: "Quality you can trust",
          qualPara:
            "We handpick each plant and gardening tool to ensure superior quality and long-lasting beauty for your indoor garden.",
        },
        {
          qualNum: "02.",
          qualHeader: "Expert Guidance",
          qualPara:
            "Our team of knowledgeable garden enthusiasts is always ready to offer guidance, tips, and tricks to help you succeed in your green endeavors.",
        },
        {
          qualNum: "03.",
          qualHeader: "Sustainable Practices",
          qualPara:
            "We are committed to sustainable and eco-friendly practices, from responsible sourcing to minimizing our carbon footprint. Join us in our mission to protect the environment.",
        },
        {
          qualNum: "04.",
          qualHeader: "Exceptional Customer Experience",
          qualPara:
            "Your satisfaction is our top priority. We strive to provide you with an exceptional customer experience from the moment you land on our website until your plants are beautifully thriving in your space",
        },
      ],
    };
  },
};
</script>

<style></style>
