<template>
  <header class=" fixed top-0 w-full flex justify-between items-center z-50  p-4 bg-[#000] text-white">
    <div class="logo">
      <h2 class="font-bold text-xl">LOGO</h2>
    </div>

    <!-- Hamburger menu button, visible on mobile -->
    <button 
      class="block md:hidden focus:outline-none" 
      @click="toggleMenu"
    >
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
      :class="`flex-col md:flex-row ${isOpen ? 'flex' : 'show'} md:flex space-y-4 md:space-y-0 space-x-0 md:space-x-6 text-xl justify-center items-center absolute md:static top-16 md:top-auto left-0 right-0 md:left-auto bg-[#FF3600] md:bg-transparent p-4 md:p-0`"
    >
      <NuxtLink to="/" class="">Home</NuxtLink>
      <NuxtLink to="/about" class="">About</NuxtLink>
      <NuxtLink to="/Services" class="">Services</NuxtLink>
      <NuxtLink to="/Events" class="">Events</NuxtLink>
      <NuxtLink to="/Portfolio" class="">Portfolio</NuxtLink>
      <NuxtLink to="/Blog" class="">Blog</NuxtLink> 
      
      
      <NuxtLink to="/Contact">


        <button class="bg-[#FF3600] hover:bg-black-700 text-white font-bold py-2 px-4 rounded">
          Contact Me
        </button>
        
      </NuxtLink> 
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    }
  }
}
</script>
