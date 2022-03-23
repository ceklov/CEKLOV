<template>
  <section id="technology" class="lower-section bg-zinc-800">
    <div>
      <h2 class="text-zinc-200">Technology Expertise</h2>
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
          mb-9
          lg:mb-6
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
          <div
            class="
              tech-carousel-caption
              carousel-caption
              text-center
            "
          >
            <h5 class="text-2xl">{{ tech.label }}</h5>
            <p class="
              hidden
              lg:block"
            >
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
/*       {
        id: 3,
        name: "JavaScript",
        src: "javascript.png",
        label: "JavaScript",
        caption: "The programming language ubiquitous in web development.",
      },
      {
        id: 4,
        name: "Angular",
        src: "angular.png",
        label: "Angular",
        caption: "Another front-end JavaScript framework I use.",
      }, */
      //{ id: 5, name: "HTML 5", src: "html.png", label: "HTML", caption: "Well, duh. Of course I know HTML." },
      //{ id: 6, name: "CSS 3", src: "", label: "", caption: "" },
      //{ id: 7, name: "Spring", src: "", label: "", caption: "" },
      //{ id: 8, name: "Microsft SQL Server", src: "", label: "", caption: "" },
      //{ id: 9, name: "MySQL", src: "", label: "", caption: "" },
      //{ id: 10, name: "Git", src: "", label: "", caption: "" },
      //{ id: 11, name: "Jenkins", src: "", label: "", caption: "" },
      //{ id: 12, name: ".NET", src: "", label: "", caption: "" },
    ];
    return { techs };
  },
};
</script>