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
      :class="`flex-col md:flex-row ${isOpen ? 'flex' : 'show'} md:flex space-y-4 md:space-y-0 space-x-0 md:space-x-10 text-xl justify-center items-center absolute md:static top-16 md:top-auto left-0 right-0 md:left-auto md:bg-transparent p-4 md:p-0`"
    >
      <NuxtLink to="/" class=""><svg xmlns="http://www.w3.org/2000/svg" fill="#FF3600" viewBox="0 0 24 24"  class="size-7">
  <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
</svg>
</NuxtLink>
      <NuxtLink to="/about" class=""><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="size-7">
  <path stroke-linecap="round" stroke-linejoin="round" fill="#FF3600" d="M15.75 6a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0ZM4.501 20.118a7.5 7.5 0 0 1 14.998 0A17.933 17.933 0 0 1 12 21.75c-2.676 0-5.216-.584-7.499-1.632Z" />
</svg>
</NuxtLink>
      <NuxtLink to="/Services" class="">
        <svg xmlns="http://www.w3.org/2000/svg"  class="size-7" viewBox="0 0 24 24"><path fill="#FF3600" d="M3 21h2v-6H3zm9.46 1l-2.93-.64l-2.93-.69a.73.73 0 0 1-.43-.26a.7.7 0 0 1-.17-.47v-4a.77.77 0 0 1 .17-.47a.8.8 0 0 1 .43-.26l4.78-.59l4.79-.6l.15.56l.15.55a.93.93 0 0 1-.15.52a.9.9 0 0 1-.4.37l-2 .5l-2 .5l1.62.66l1.63.65l2.27-.64l2.21-.69a.78.78 0 0 1 .58.08a.73.73 0 0 1 .36.46l.19.77l.2.76a.77.77 0 0 1-.08.56a.78.78 0 0 1-.46.35l-3.63 1l-3.63 1a1.4 1.4 0 0 1-.36 0a1.1 1.1 0 0 1-.36.02M9 4L7 6L5 8l2 2l2 2l.7-.7l.7-.7l-1.3-1.3L7.8 8l1.3-1.3l1.3-1.3l-.7-.7zm6 0l-.7.7l-.7.7l1.3 1.3L16.2 8l-1.3 1.3l-1.3 1.3l.7.7l.7.7l2-2l2-2l-2-2z"/></svg>
      </NuxtLink>
      <NuxtLink to="/Events" class="">
        <svg xmlns="http://www.w3.org/2000/svg" class="size-7" viewBox="0 0 24 24"><path fill="#FF3600" d="M21 17V8H7v9zm0-14a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h1V1h2v2h8V1h2v2zm-3.47 8.06l-4.44 4.44l-2.68-2.68l1.06-1.06l1.62 1.62L16.47 10zM3 21h14v2H3a2 2 0 0 1-2-2V9h2z"/></svg>
      </NuxtLink>
      <NuxtLink to="/Portfolio" class=""><svg xmlns="http://www.w3.org/2000/svg" class="size-7" viewBox="0 0 20 20"><path fill="#FF3600" d="M4 5H.78c-.37 0-.74.32-.69.84l1.56 9.99S3.5 8.47 3.86 6.7c.11-.53.61-.7.98-.7H10s-.7-2.08-.77-2.31C9.11 3.25 8.89 3 8.45 3H5.14c-.36 0-.7.23-.8.64C4.25 4.04 4 5 4 5m4.88 0h-4s.42-1 .87-1h2.13c.48 0 1 1 1 1M2.67 16.25c-.31.47-.76.75-1.26.75h15.73c.54 0 .92-.31 1.03-.83c.44-2.19 1.68-8.44 1.68-8.44c.07-.5-.3-.73-.62-.73H16V5.53c0-.16-.26-.53-.66-.53h-3.76c-.52 0-.87.58-.87.58L10 7H5.59c-.32 0-.63.19-.69.5c0 0-1.59 6.7-1.72 7.33c-.07.37-.22.99-.51 1.42M15.38 7H11s.58-1 1.13-1h2.29c.71 0 .96 1 .96 1"/></svg></NuxtLink>
      <NuxtLink to="/Blog" class="">
      <svg xmlns="http://www.w3.org/2000/svg" class="size-7" viewBox="0 0 24 24"><path fill="#FF3600" d="M12.526 11.695c1.84-.382 3.367-2.044 3.367-4.478c0-2.604-1.9-4.97-5.615-4.97H0v19.506h10.6c3.75 0 5.683-2.341 5.683-5.292c-.009-2.426-1.646-4.444-3.757-4.766m-8.37-5.793h5.207c1.407 0 2.28.849 2.28 2.044c0 1.255-.881 2.044-2.28 2.044H4.155zM9.54 18.098H4.155v-4.444h5.386c1.61 0 2.484.992 2.484 2.222c.009 1.399-.932 2.222-2.484 2.222zM21.396 2.28c-1.255 0-2.315 1.052-2.315 2.307s.882 2.103 1.993 2.103c.238 0 .467-.025.56-.085c-.238 1.052-1.315 2.282-2.256 2.782l1.611 1.314C22.796 9.422 24 7.462 24 5.266c0-1.9-1.23-2.985-2.604-2.985Z"/></svg>
      </NuxtLink> 
      
      
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
