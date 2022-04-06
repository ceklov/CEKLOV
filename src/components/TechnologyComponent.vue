<template>
  <section id="technology" class="lower-section bg-zinc-800">
    <div>
      <h2 class="text-zinc-200">Technology</h2>
    </div>

    <div>
      <h4>Including but not limited to</h4>
    </div>

    <Waypoint
      :options="options"
      @change="startSliding"
    >
      <swiper
        id="tech-swiper"
        :modules="modules"
        :slides-per-view="1"
        :space-between="10"
        navigation
        :speed="1000"
        :pagination="{ clickable: true }"
        class="my-9"
      >
        <swiper-slide
          v-for="(tech, index) in techs"
          :key="index"
          :virtualIndex="index"
          class="px-3 flex flex-col justify-center"
          data-swiper-autoplay="4200"
        >
          <img
            :src="require('@/assets/technology/' + tech.src)"
            :alt="tech.name"
          />
          <h5 class="text-zinc-200 text-2xl mt-6 lg:mt-5">
            {{ tech.name }}
          </h5>
          <p class="text-zinc-200 mt-6 mb-12 lg:mt-5">
            {{ tech.caption }}
          </p>
        </swiper-slide>
      </swiper>
    </Waypoint>
  </section>
</template>

<script>
  import { Navigation, Pagination, A11y, Autoplay } from 'swiper';
  import { Swiper, SwiperSlide } from 'swiper/vue';
  import 'swiper/css';
  import 'swiper/css/navigation';
  import 'swiper/css/pagination';

  import { Waypoint } from "vue-waypoint";

export default {
  name: "TechnologyComponent",
  components: {
    Swiper,
    SwiperSlide,
    Waypoint
  },
  setup() {
    const options = {
      root: document.getElementById("services-wrapper"),
      rootMargin: "0px",
      threshold: 0.75
    }

    const startSliding = (waypointState) => {
      if (waypointState.going === "IN" && !document.querySelector("#tech-swiper").swiper.autoplay.running) {
        document.querySelector("#tech-swiper").swiper.autoplay.start();
      }
    }

    const techs = [
      {
        name: "Java",
        src: "java.svg",
        caption:
          "The back-end programming language with which I have the most experience.",
      },
      {
        name: "Vue.js",
        src: "vue.svg",
        caption:
          "The front-end JavaScript framework with which I have the most experience.",
      },
      {
        name: "JavaScript",
        src: "javascript.svg",
        caption: "The programming language ubiquitous in web app development.",
      },
      {
        name: "Angular",
        src: "angular.svg",
        caption:
          "Another front-end JavaScript framework I have been known to use.",
      },
      {
        name: "HTML 5",
        src: "html.svg",
        caption:
          "It's hard to make it very far without knowledge of this markup.",
      },
      {
        name: "CSS 3",
        src: "css.svg",
        caption:
          "Websites would just be so bland without a little extra style.",
      },
      {
        name: "Spring Framework",
        src: "spring.svg",
        caption:
          "Spring Boot, Data, Security, and more for my work with Java.",
      },
      {
        name: "Microsft SQL Server",
        src: "ms-sql-server.svg",
        caption:
          "How I have mainly (but not exclusively) worked with SQL and databases.",
      },
      {
        name: "Git",
        src: "git.svg",
        caption:
          "My primary source control for both personal and professional work.",
      },
      {
        name: "Jenkins",
        src: "jenkins.svg",
        caption:
          "My primary tool for building and deploying.",
      },
    ];

    return {
      startSliding,
      options,
      techs,
      modules: [Navigation, Pagination, A11y, Autoplay],
    };
  },
};
</script>

<style scoped>

.swiper-button-prev {
  right: 0px;
}

.swiper-button-next {
  left: 0px;
}

</style>

