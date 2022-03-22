<template>
  <section id="links" class="lower-section">
    <div>
      <h2>Links</h2>
    </div>
    <div>
      <h4>Just some extras</h4>
    </div>
    <div v-for="link in links" :key="link.id">
      <a :href="link.link">{{ link.text }}</a>
    </div>
  </section>
</template>

<script>
export default {
  name: "LinksComponent",
  components: {},
  setup() {
    const links = [
      { id: 1, link: "https://www.github.com/ceklov/", text: "GitHub" },
      {
        id: 2,
        link: "https://www.linkedin.com/in/cody-eklov-b8507b97/",
        text: "LinkedIn",
      },
    ];
    return { links };
  },
};
</script>