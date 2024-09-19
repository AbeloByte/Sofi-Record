<template>
  <section
    class="relative flex items-center justify-start h-screen bg-cover bg-center bg-no-repeat hero-section sm:p-0"
  >
    <div
      class="max-w-full md:max-w-xl lg:max-w-2xl text-white z-20 ml:5 md:ml-36 lg:ml-40 p-4"
    >
      <h1
        class="text-6xl text-center md:text-4xl md:text-left lg:text-7xl lg:md:text-4xl font-bold mb-4 md:leading-20 pt-24"
      >
        Crafting Soundscapes That Elevate Your Music Experience
      </h1>
      <p
        class="text-xl md:text-lg lg:text-xl mb-6 text-gray-300 leading-relaxed contentDescription" 
      >
        Discover the artistry and innovation behind sound—where every beat tells
        a story and every track is a masterpiece.
      </p>
      <NuxtLink to="/About">
        <button
          class="py-2 px-4 md:py-3 md:px-6 text-base md:text-lg lg:text-xl font-bold bg-[#FF3600] rounded-lg text-white border-none cursor-pointer transition duration-300 ease-in-out hover:bg-red-700"
        >
          Learn More
        </button>
      </NuxtLink>
    </div>
    <div class="hidden lg:block">
      <img
        src="../public/mic down.png"
        alt="Mic Image"
        class="fixed sm:top-[-70px] sm:right-[-5.0rem] z-20"
      />
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.hero-section {
  background-image: url("/HeroImage.png");
}
</style>
