  <template>
    <div class="bg-[#14141E]">
        <section id="events" class="events  py-16 ">
        <div class=" lg:w-[80%] mx-auto ">
          <h2 class="text-3xl md:text-4xl font-bold text-center mb-8">Upcoming <span class="text-[#FF3600]">Events</span></h2>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Event Card 1-->
            <div class="bg-white p-4 rounded-lg shadow-md">
              <img src="/Event1.png"  alt="Event" class="w-full h-40 object-cover mb-4 rounded">
              <h3 class="text-xl font-semibold mb-2 text-[#FF3600]">Event Title</h3>
              <p class="text-gray-600">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
              <NuxtLink to="/Events">
                    <button class="py-1 px-4 mt-4 md:py-3 md:px-6 text-base md:text-lg lg:text-xl font-bold bg-[#FF3600] rounded-lg text-white border-none cursor-pointer transition duration-300 ease-in-out hover:bg-red-700">See Details</button>
              </NuxtLink>
            </div>
            <!-- Event Card 2-->
            <div class="bg-white p-4 rounded-lg shadow-md">
              <img  src="/Event2.png" alt="Event" class="w-full h-40 object-cover mb-4 rounded">
              <h3 class="text-xl font-semibold mb-2 text-[#FF3600]">Event Title</h3>
              <p class="text-gray-600">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
              
              <NuxtLink to="/Events">
                    <button class="py-1 px-4 mt-4 md:py-3 md:px-6 text-base md:text-lg lg:text-xl font-bold bg-[#FF3600] rounded-lg text-white border-none cursor-pointer transition duration-300 ease-in-out hover:bg-red-700">See Details</button>
              </NuxtLink>
            </div>
            <!-- Event Card 3-->
            <div class="bg-white p-4 rounded-lg shadow-md">
              <img src="/Event3.png" alt="Event" class="w-full h-40 object-cover mb-4 rounded">
              <h3 class="text-xl font-semibold mb-2 text-[#FF3600]">Event Title</h3>
              <p class="text-gray-600">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum, ac aliquet odio mattis.</p>
              <NuxtLink to="">
                    <button class="py-1 px-4 mt-4 md:py-3 md:px-6 text-base md:text-lg lg:text-xl font-bold bg-[#FF3600] rounded-lg text-white border-none cursor-pointer transition duration-300 ease-in-out hover:bg-red-700">See Details</button>
              </NuxtLink>
            </div>
          </div>
        </div>
      </section>
    </div>
  </template>
  
  <script setup>
  
  </script>
  
  <style lang="scss" scoped>
  
  </style>






