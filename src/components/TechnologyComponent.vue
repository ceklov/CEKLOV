<template>
  <section id="technology" class="lower-section bg-zinc-800">
    <div>
      <h2 class="text-zinc-200">My Technology</h2>
    </div>

    <div>
      <h4>Including but not limited to</h4>
    </div>

    <div
      id="tech-carousel"
      class="carousel slide relative flex justify-center"
      data-bs-ride="carousel"
    >
      <div
        id="tech-carousel-indicators-container"
        class="
          carousel-indicators
          absolute
          right-0
          bottom-0
          left-0
          flex
          justify-center
          mb-20
          lg:mb-32
        "
      >
        <button
          v-for="tech in techs"
          :key="tech.id"
          type="button"
          data-bs-target="#tech-carousel"
          :data-bs-slide-to="tech.id - 1"
          :class="tech.id == 1 ? 'active' : ''"
          :aria-current="tech.id == 1 ? 'true' : 'false'"
          :aria-label="'Slide ' + tech.id"
        ></button>
      </div>
      <div class="carousel-inner relative w-96 h-80">
        <div
          v-for="tech in techs"
          :key="tech.id"
          :class="
            tech.id == 1
              ? 'tech-carousel-item carousel-item active relative float-left w-full'
              : 'tech-carousel-item carousel-item relative float-left w-full'
          "
        >
          <img
            :src="require('@/assets/technology/' + tech.src)"
            :alt="tech.name"
          />
          <div class="tech-carousel-caption carousel-caption text-center">
            <h5 class="text-2xl">{{ tech.label }}</h5>
            <p class="mt-9 lg:mt-2">
              {{ tech.caption }}
            </p>
          </div>
        </div>
      </div>
      <button
        class="
          carousel-control-prev
          absolute
          top-0
          bottom-0
          flex
          items-center
          justify-center
          p-0
          text-center
          border-0
          hover:outline-none hover:no-underline
          focus:outline-none focus:no-underline
          left-0
          md:left-20
          lg:left-28
        "
        type="button"
        data-bs-target="#tech-carousel"
        data-bs-slide="prev"
      >
        <span
          class="carousel-control-prev-icon inline-block bg-no-repeat"
          aria-hidden="true"
        ></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button
        class="
          carousel-control-next
          absolute
          top-0
          bottom-0
          flex
          items-center
          justify-center
          p-0
          text-center
          border-0
          hover:outline-none hover:no-underline
          focus:outline-none focus:no-underline
          right-0
          md:right-20
          lg:right-28
        "
        type="button"
        data-bs-target="#tech-carousel"
        data-bs-slide="next"
      >
        <span
          class="carousel-control-next-icon inline-block bg-no-repeat"
          aria-hidden="true"
        ></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </section>
</template>

<script>
export default {
  name: "TechnologyComponent",
  components: {},
  setup() {
    const techs = [
      {
        id: 1,
        name: "Java",
        src: "java.svg",
        label: "Java",
        caption:
          "The back-end programming language with which I have the most experience.",
      },
      {
        id: 2,
        name: "Vue.js",
        src: "vue.svg",
        label: "Vue.js",
        caption:
          "The front-end JavaScript framework with which I have the most experience.",
      },
      {
        id: 3,
        name: "JavaScript",
        src: "javascript.svg",
        label: "JavaScript",
        caption: "The programming language ubiquitous in web development.",
      },
      {
        id: 4,
        name: "Angular",
        src: "angular.svg",
        label: "Angular",
        caption:
          "Another front-end JavaScript framework I have been known to use.",
      },
      {
        id: 5,
        name: "HTML 5",
        src: "html.svg",
        label: "HyperText Markup Language",
        caption:
          "No surprise here. You must have some knowledge of this markup.",
      },
      {
        id: 6,
        name: "CSS 3",
        src: "css.svg",
        label: "Cascading Style Sheets",
        caption:
          "Websites would just be so bland without a little extra style.",
      },
      {
        id: 7,
        name: "Spring",
        src: "spring.svg",
        label: "Spring Framework",
        caption:
          "Spring Boot, Data, Security, and more complements my work with Java.",
      },
      {
        id: 8,
        name: "Microsft SQL Server",
        src: "ms-sql-server.svg",
        label: "Microsoft SQL Server",
        caption:
          "How I have mainly (but not exclusively) worked with data using SQL.",
      },
      {
        id: 9,
        name: "Git",
        src: "git.svg",
        label: "Git",
        caption:
          "GitHub and GitLab are my primary project repositories. I also enjoy the Git command line.",
      },
      {
        id: 10,
        name: "Jenkins",
        src: "jenkins.svg",
        label: "Jenkins",
        caption:
          "It's hard to develop software without a reliable source of building and deploying like Jenkins.",
      },
    ];
    return { techs };
  },
};
</script>