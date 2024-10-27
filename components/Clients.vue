
  

  <!--  -->

  <template>
    <section id="carousel" class="relative overflow-hidden py-16  bg-[#14141E]">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl md:text-4xl font-bold text mb-8 ml-[150px]">Our <span class="text-[#FF3600]">Clients</span> </h2>
        <div class="relative overflow-hidden mx-8">
          <!-- Carousel Wrapper -->
          <div class="carousel flex gap-60 animate-slide">
            <!-- Carousel Images -->
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/HopeLogo.png" alt="Image 1" class="object-cover w-full h-full rounded">
            </div>
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/Balageru.png" alt="Image 2" class="object-cover w-full h-full rounded">
            </div>
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/FanaTv.png" alt="Image 3" class="object-cover w-full h-full rounded">
            </div>
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/Sewasew.png" alt="Image 4" class="object-cover w-full h-full rounded">
            </div>
  
            <!-- Duplicate Images for Seamless Loop -->
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/HopeLogo.png" alt="Image 1" class="object-cover w-full h-full rounded">
            </div>
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/Sewasew.png" alt="Image 2" class="object-cover w-full h-full rounded">
            </div>
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/" alt="Image 3" class="object-cover w-full h-full rounded">
            </div>
            <div class="flex-shrink-0 w-full md:w-64 h-40 mx-2">
              <img src="/mic.png" alt="Image 4" class="object-cover w-full h-full rounded">
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  // Any necessary JavaScript can be added here.
  </script>
  
  <style scoped>
  /* Custom CSS for continuous sliding animation */
  @keyframes slide {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }
  
  .carousel {
    width: 200%; /* Width is doubled to fit both original and duplicated images */
    display: flex;
  }
  
  .animate-slide {
    animation: slide 20s linear infinite; /* Adjust timing for smooth sliding */
  }
  </style>
  