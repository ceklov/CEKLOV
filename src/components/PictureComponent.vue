<template>
  <section id="home" class="landing-picture h-screen flex items-center justify-center bg-fixed">
    <div
      class="absolute top-0 left-0 w-full h-full bg-zinc-800 opacity-60 z-10"
    ></div>

    <div class="flex flex-col justify-center items-center z-10">
      <div>
        <h1
          class="
            text-center text-5xl
            md:text-6xl
            mt-48
            md:m-24
            uppercase
            text-zinc-200
            font-medium
          "
        >
          Cody Eklov
        </h1>
      </div>

      <div class="flex lg:flex-row flex-col flex-wrap justify-center mt-7 max-w-screen-2xl">
        <div class="flex flex-col md:flex-row text-center items-center w-80 lg:w-96 mx-2 my-7 md:block">
          <h3 class="text-2xl lg:text-3xl font-medium text-zinc-300">Software Development</h3>
        </div>
        <div class="flex flex-col md:flex-row text-center items-center w-80 lg:w-96 mx-2 my-7 md:block">
          <h3 class="text-2xl lg:text-3xl font-medium text-zinc-300">Web Design</h3>
        </div>
        <div class="flex flex-col md:flex-row text-center items-center w-80 lg:w-96 mx-2 my-7 md:block">
          <h3 class="text-2xl lg:text-3xl font-medium text-zinc-300">Quality</h3>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "PictureComponent",
  components: {},
};
</script>