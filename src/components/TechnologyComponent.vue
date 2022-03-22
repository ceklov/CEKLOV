<template>
  <section id="technology" class="lower-section">
    <div>
      <h2>Technology Expertise</h2>
    </div>
    <div>
      <h4>Including but not limited to</h4>
    </div>
    <div v-for="tech in techs" :key="tech.id">
      {{ tech.name }}
    </div>
  </section>
</template>

<script>
export default {
  name: "TechnologyComponent",
  components: {},
  setup() {
    const techs = [
      { id: 1, name: "Java" },
      { id: 2, name: "Vue.js" },
      { id: 3, name: "Angular" },
      { id: 4, name: "HTML 5" },
      { id: 5, name: "CSS 3" },
      { id: 6, name: "JavaScript" },
      { id: 7, name: "Spring" },
      { id: 8, name: "Microsft SQL Server" },
      { id: 9, name: "MySQL" },
      { id: 10, name: "Git" },
      { id: 11, name: "Jenkins" },
      { id: 12, name: ".NET" },
    ];
    return { techs };
  },
};
</script>