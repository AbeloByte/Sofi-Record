<template>
  <header
    class="fixed top-0 w-full flex justify-between items-center z-50 p-2 bg-[#000] text-white"
  >
    <div class="logo">
      <NuxtLink to="/"><h2 class="font-bold text-xl">LOGO</h2></NuxtLink>
    </div>

    <!-- Hamburger menu button, visible on mobile -->
    <button class="block md:hidden focus:outline-none" @click="toggleMenu">
      <svg
        class="w-6 h-6 transition-transform duration-300 transform"
        :class="isOpen ? 'rotate-45' : ''"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          v-if="!isOpen"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16M4 18h16"
        ></path>
        <path
          v-else
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        ></path>
      </svg>
    </button>

    <!-- Navigation links -->
<nav
  :class="`flex-col md:flex-row ${isOpen ? 'flex' : 'hidden'} md:flex space-y-4 md:space-y-0 space-x-0 md:space-x-10 text-xl justify-center items-center absolute md:static top-16 md:top-auto left-0 right-0 md:left-auto md:bg-transparent p-4 md:p-0`"
>

      <NuxtLink to="/" class="]"><House color="red" /></NuxtLink>
      <NuxtLink to="/about" class=""><UserRound color="#FF3600" /></NuxtLink>
      <NuxtLink to="/Services" class="">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="size-7"
          viewBox="0 0 24 24"
        >
          <path
            fill="#FF3600"
            d="M3 21h2v-6H3zm9.46 1l-2.93-.64l-2.93-.69a.73.73 0 0 1-.43-.26a.7.7 0 0 1-.17-.47v-4a.77.77 0 0 1 .17-.47a.8.8 0 0 1 .43-.26l4.78-.59l4.79-.6l.15.56l.15.55a.93.93 0 0 1-.15.52a.9.9 0 0 1-.4.37l-2 .5l-2 .5l1.62.66l1.63.65l2.27-.64l2.21-.69a.78.78 0 0 1 .58.08a.73.73 0 0 1 .36.46l.19.77l.2.76a.77.77 0 0 1-.08.56a.78.78 0 0 1-.46.35l-3.63 1l-3.63 1a1.4 1.4 0 0 1-.36 0a1.1 1.1 0 0 1-.36.02M9 4L7 6L5 8l2 2l2 2l.7-.7l.7-.7l-1.3-1.3L7.8 8l1.3-1.3l1.3-1.3l-.7-.7zm6 0l-.7.7l-.7.7l1.3 1.3L16.2 8l-1.3 1.3l-1.3 1.3l.7.7l.7.7l2-2l2-2l-2-2z"
          />
        </svg>
      </NuxtLink>
      <NuxtLink to="/Events" class=""
        ><CalendarClock color="#FF3600"
      /></NuxtLink>
      <NuxtLink to="/Portfolio" class="">
        <Images color="red" />
      </NuxtLink>
      <NuxtLink to="/Blog" class=":links">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="size-7"
          viewBox="0 0 24 24"
        >
          <path
            fill="#FF3600"
            d="M12.526 11.695c1.84-.382 3.367-2.044 3.367-4.478c0-2.604-1.9-4.97-5.615-4.97H0v19.506h10.6c3.75 0 5.683-2.341 5.683-5.292c-.009-2.426-1.646-4.444-3.757-4.766m-8.37-5.793h5.207c1.407 0 2.28.849 2.28 2.044c0 1.255-.881 2.044-2.28 2.044H4.155zM9.54 18.098H4.155v-4.444h5.386c1.61 0 2.484.992 2.484 2.222c.009 1.399-.932 2.222-2.484 2.222zM21.396 2.28c-1.255 0-2.315 1.052-2.315 2.307s.882 2.103 1.993 2.103c.238 0 .467-.025.56-.085c-.238 1.052-1.315 2.282-2.256 2.782l1.611 1.314C22.796 9.422 24 7.462 24 5.266c0-1.9-1.23-2.985-2.604-2.985Z"
          />
        </svg>
      </NuxtLink>
      <NuxtLink to="/Contact">
        <button
          class="bg-[#FF3600] hover:bg-black-700 text-white font-bold py-2 px-4 rounded"
        >
          Contact Me
        </button>
      </NuxtLink>
    </nav>
  </header>
</template>

<script setup>
import { ref } from "vue";
import { House } from "lucide-vue-next";
import { UserSearch } from "lucide-vue-next";
import { CalendarClock } from "lucide-vue-next";
import { Images } from "lucide-vue-next";
import { UserRound } from "lucide-vue-next";
// Reactive state for managing menu open/close
const isOpen = ref(false);

// Function to toggle menu open/close
const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style scoped>
nav a:hover {
  color: #fff;
  /* box-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #fff; */
  filter: drop-shadow(0 0 20px #fff);
}



</style>
