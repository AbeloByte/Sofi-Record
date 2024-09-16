<template>
 
           <!-- Services Section -->
      <section id="services" class="services md:mx-9 lg:mx-14 h-[100vh]">
        <div class="mt-5">
        <h1 class="text-3xl md:text-4xl font-bold text-[#FF3600]">Service</h1>
          <h2 class="text-2xl font-bold ">Explore the World of Music  Production</h2>
          <p class="py-4 md:text-xl">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis. .</p>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4  rounded-full">
            <!-- Service Card  1-->   
            <div class="bg-[#363636] p-8  h-[260px]">
              <IconsTherapy/>
              <h3 class="text-xl font-bold mb-2 mt-3"><span class="text-[#FF3600]">Music</span>  Therapy</h3>
              <p class="text-gray-300">Worem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
            </div>
            <!-- Service Card  2-->   
            <div class="bg-white p-8  h-[260px]">
              <IconsMastering/>
              <h3 class="text-xl font-bold mb-2 mt-3 text-black"><span class="text-[#FF3600]">Tv Program</span> intro</h3>
              <p class="text-gray-600">Worem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
            </div>
            <!-- Service Card  3-->   
            <div class="bg-[#363636] p-8  h-[260px]">
              <IconsMixing/>
              <h3 class="text-xl font-semibold mb-2 mt-3">Tv Program  Mixing</h3>
              <p class="text-gray-300">Worem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
            </div>
            <!-- Service Card  4-->   
            <div class="bg-[#363636] p-8  h-[260px]">
              <IconsClassicTone/>              
              <h3 class="text-xl font-bold mb-2 mt-3"><span class="text-[#FF3600]">Music</span>   Mixing</h3>
              <p class="text-gray-300">Worem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
            </div>
            <!-- Service Card  5-->   
            <div class="bg-white p-8  h-[260px]">
              <IconsMastering/>

              <h3 class="text-xl font-bold text-black mb-2 mt-3"><span class="text-[#FF3600]">Music</span> Production</h3>
              <p class="text-gray-600">Worem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
            </div>
            <!-- Service Card  6-->   
            <div class="bg-[#363636] p-8  h-[260px]">
              <IconsMusicTherapy/>

              <h3 class="text-xl font-semibold mb-2 mt-3"><span class="text-[#FF3600]">Music</span>   Therapy</h3>
              <p class="text-gray-300">Worem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
            </div>
          </div>
          
          <NuxtLink to="/Services">
          <button class="py-4 m-3 px-4 md:py-3 md:px-6 text-base md:text-lg lg:text-xl font-bold bg-[#FF3600] rounded-lg text-white border-none cursor-pointer transition duration-300 ease-in-out hover:bg-red-700">Read More</button>
        </NuxtLink>
        </div>
        
      </section>

</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>