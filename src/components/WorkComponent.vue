<template>
  <section id="work">
    <div>
      <h2>My Work</h2>
    </div>
    <div>
      <h3>Take a look</h3>
    </div>
    <div v-for="project in projects" :key="project.id">
      {{ project.name }}
    </div>
  </section>
</template>

<script>
export default {
  name: "WorkComponent",
  components: {},
  setup() {
    const projects = [
      { id: 1, name: "Example 1", link: "", img: "" },
      { id: 2, name: "Example 2", link: "", img: "" },
      { id: 3, name: "Example 3", link: "", img: "" },
    ];
    return { projects };
  },
};
</script>