<template>
  <section class="footer__section">
    <p>
      © Greenery. All Rights Reserved 2023. Licensing Webflow Templatesby
      128.digital. Powered by Webflow
    </p>

    <div class="socials__container">
      <a
        :href="links.link"
        v-for="links in socials"
        :key="links.id"
        target="_blank"
        >{{ links.socialMedia }}</a
      >
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      socials: [
        {
          socialMedia: "Facebook",
          link: "https://www.facebook.com/",
        },
        {
          socialMedia: "Instagram",
          link: "https://www.instagram.com/",
        },
        {
          socialMedia: "Twitter",
          link: "https://www.twitter.com/",
        },
      ],
    };
  },
};
</script>

<style></style>
