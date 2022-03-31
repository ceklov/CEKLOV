<template>
  <header class="absolute w-full z-50">
    <nav
      class="flex flex-row flex-wrap justify-between my-3 lg:items-start"
      role="navigation"
    >
      <div class="flex items-center ml-3">
        <a class="flex" href="/">
          <img src="../assets/favicon-32x32.png" class="opacity-90" />
        </a>
      </div>

      <div
        id="lg-nav-content"
        class="hidden lg:flex mr-3 w-auto py-0 items-center"
      >
        <ul class="flex text-sm font-medium tracking-widest text-zinc-200 mt-2">
          <a 
            v-for="(link, index) in links"
            :key="index"
            :href="'/#' + link.name"
            @click="close">
            <li
              class="
                uppercase
                hover:bg-zinc-200 hover:text-zinc-800 hover:font-semibold
                px-2
                mb-3
                w-36
              "
            >
              {{ link.name }}
            </li>
          </a>
          <a href="/eklov-resume.pdf" target="_blank" @click="close">
            <li
              class="
                uppercase
                hover:bg-zinc-200 hover:text-zinc-800 hover:font-semibold
                px-2
                mb-3
                w-28
              "
            >
              Resume
            </li>
          </a>
        </ul>
      </div>

      <div class="inline-block h-8 mr-3 lg:hidden">
        <button id="nav-button" class="h-full w-full" @click="isOpen">
          <svg
            class="h-full w-auto"
            xmlns="http://www.w3.org/2000/svg"
            width="192"
            height="192"
            fill="#E4E4E7"
            viewBox="0 0 256 256"
          >
            <rect width="256" height="256" fill="none"></rect>
            <line
              x1="40"
              y1="128"
              x2="216"
              y2="128"
              stroke="#E4E4E7"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="16"
            ></line>
            <line
              x1="40"
              y1="64"
              x2="216"
              y2="64"
              stroke="#E4E4E7"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="16"
            ></line>
            <line
              x1="40"
              y1="192"
              x2="216"
              y2="192"
              stroke="#E4E4E7"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="16"
            ></line>
          </svg>
        </button>
      </div>

      <div id="sm-nav-content" v-show="show" class="w-full mr-3 lg:hidden">
        <ul
          class="
            flex flex-col
            items-end
            text-sm
            font-medium
            tracking-widest
            text-zinc-200
            mt-2
          "
        >
          <a
            v-for="(link, index) in links"
            :key="index"
            :href="'/#' + link.name"
            @click="close"
          >
            <li
              class="
                text-right
                uppercase
                px-2
                mb-4
                w-36
                hover:bg-zinc-200 hover:text-zinc-800 hover:font-semibold
              "
            >
              {{ link.name }}
            </li>
          </a>

          <a href="/eklov-resume.pdf" target="_blank" @click="close">
            <li
              class="
                text-right
                uppercase
                px-2
                mb-4
                w-36
                hover:bg-zinc-200 hover:text-zinc-800 hover:font-semibold
              "
            >
              Resume
            </li>
          </a>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
import { ref } from "vue";

export default {
  name: "HeaderComponent",
  components: {},
  setup() {
    const links = [
      { name: "services" },
      { name: "technology" },
      { name: "contact" },
    ];

    let show = ref(false);
    const isOpen = () => (show.value = !show.value);
    const close = () => (show.value = false);
    return { show, isOpen, close, links };
  },
};
</script>