<template>
  <section class="flex justify-center items-center h-screen">
    <div class="lg:mx-14">
    
    <!-- Parent Div with Custom Width and Height -->
    <div
      class="flex flex-col-reverse md:flex-row items-center justify-between bg-[#2A2727] rounded-lg md:p-14 mx-auto  gap-10 shadow-[#000000]
      shadow-md hover:shadow-xl hover:scale-105 hover:z-10 transition-all duration-300  hover:shadow-black p-6
      ">
      

      <!-- About Me Content -->
      <div class="md:w-1/2 mt-6 md:mt-0">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4 text-center">
          About <span class="text-[#FF3600]">Me</span>
          
        </h2>
        <p class="text-white text-lg mb-6">
          Corem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Curabitur tempus urna at turpis condimentum lobortis. Ut commodo efficitur neque.Corem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Curabitur tempus urna at turpis condimentum lobortis. Ut commodo efficitur neque.
        </p>
       
       <NuxtLink to="/About"> 
        <button class="py-4 m-3 px-4 md:py-3 md:px-6 text-base md:text-lg lg:text-xl font-bold bg-[#FF3600] rounded-lg text-white border-none cursor-pointer transition duration-300 ease-in-out hover:bg-red-700">Read More</button>
       </NuxtLink>
      </div>

      <!-- Photo -->
      <div class="md:w-1/2 flex justify-center">
        <img src="/personal.jpg" alt="Profile Photo" class="w-full h-full rounded object-cover shadow-lg">
      </div>
      
    </div>
  </div>
  </section>

</template>

<script setup>

</script>

<style scoped>
</style>
