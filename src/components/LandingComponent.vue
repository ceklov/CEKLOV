<template>
  <section
    id="home"
    class="h-screen flex items-center justify-center"
  >
    <div
      class="absolute top-0 left-0 w-full h-screen bg-zinc-800 opacity-60 z-10"
    ></div>

    <div class="flex flex-col justify-center items-center z-10">
      <div>
        <h1
          class="
            text-center
            text-6xl
            mt-48
            lg:m-24
            uppercase
            text-zinc-200
            font-medium
          "
        >
          Cody Eklov
        </h1>
      </div>

      <div
        class="
          flex
          lg:flex-row
          flex-col flex-wrap
          justify-center
          mt-7
          max-w-screen-2xl
        "
      >
        <div
          v-for="(caption, index) in captions"
          :key="index"
          class="
            flex flex-col
            md:flex-row
            text-center
            items-center
            w-80
            lg:w-88
            mx-2
            my-7
            md:block
          "
        >
          <h3>
            <a :href="'/#services'" class="cursor-default">
              {{ caption.text }}
            </a>
          </h3>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "LandingComponent",
  components: {},
  setup() {
    const captions = [
      { text: "Software" },
      { text: "Design" },
      { text: "Quality" },
    ];
    return { captions };
  },
};
</script>

<style scoped>

  #home {
    background: url(../assets/laptop.avif);
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
  }

</style>