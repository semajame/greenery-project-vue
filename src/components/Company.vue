<template>
  <section class="company__section">
    <h3>{{ companyHeader }}</h3>

    <h2>
      {{ companyPara }}
      <span class="span__color__green">{{ companyGreen }}</span>
      {{ companyParaTwo }}

      <span class="span__color__green">{{ companyGreenTwo }}</span>
    </h2>

    <p>
      {{ companyParaThree }}
    </p>
  </section>
</template>

<script>
export default {
  data() {
    return {
      companyHeader: "Company",
      companyGreen: "plants and gardening",
      companyPara:
        " We are your one-stop destination for all things related to",
      companyParaTwo:
        ", providing you with high-quality products and expert advice ",
      companyGreenTwo: "to help you nurture your green space.",
      companyParaThree:
        "— Transform your living space into a serene oasis with our diverse collection of indoor plants. From elegant ferns to exotic orchids, we have carefully curated a range of green companions to suit every style and preference.",
    };
  },
};
</script>

<style></style>
