<script setup >

</script>

<template>
    <footer class="bg-black text-white py-10 ">
      <div class="lg:w-[86%] md:w-[95%] w-[97%] mx-auto  grid grid-cols-1 md:grid-cols-3 gap-10">
        <div class="lg:w-[80%] mx-auto">
        <!-- Logo and Address Section -->
        <div class="flex flex-col space-y-4">
          <h2 class="text-2xl font-bold">Logo</h2>
          <div>
            <p class="font-semibold">Address</p>
            <p>Addis Abeba Sample St, Bole 2000</p>
          </div>
          <div>
            <p class="font-semibold">Contact</p>
            <p>+251912345678</p>
          </div>
        </div>
      </div>
  
        <!-- Social Links and Navigation -->
        <div class="flex flex-col space-y-4 items-start">
          <nav class="flex space-x-4">
            <a to="#" class="hover:underline">Home</a>
            <a to="#" class="hover:underline">About</a>
            <a to="#" class="hover:underline">Services</a>
            <a to="#" class="hover:underline">Feedback</a>
            <a to="#" class="hover:underline">Blog</a>
            <a to="#" class="hover:underline">Portfolio</a>
          </nav>
          <div class="flex space-x-4">
            <NuxtLink to="#">
              <Icon name="uil:facebook" style="color: white ;width : 40px; height: 40px  ;width : 40px; height: 40px " /></NuxtLink>
            <NuxtLink to="#">
              <Icon name="uil:whatsapp" style="color: white ;width : 40px; height: 40px  ;width : 40px; height: 40px " />
            </NuxtLink>
            <NuxtLink to="#">
              <Icon name="uil:twitter" style="color: white ;width : 40px; height: 40px  ;width : 40px; height: 40px " />
            </NuxtLink>
            <NuxtLink to="#">
              <Icon name="uil:youtube" style="color:white;width : 40px; height: 40px " />
            </NuxtLink>
            <NuxtLink to="#">
              <Icon name="uil:" style="color: white ;width : 40px; height: 40px  ;width : 40px; height: 40px " />
            </NuxtLink>
          </div>
        </div>
  
        <!-- Subscription Section -->
        <div class="flex flex-col space-y-4">
          <p class="font-semibold">Subscribe to the Blog Post</p>
          <div class="flex ">
            <input
              type="email"
              placeholder="Type your Email here"
              class="bg-gray-800 text-white py-2 px-4 w-full border border-gray-700 focus:outline-none"
            />
            <button class="bg-[#FF3600] text-white px-6 py-2 border-full border-zinc-500">Subscribe</button>
          </div>
        </div>
      </div>
  
      <!-- Bottom Section -->
      <div class="container mx-auto mt-10 border-t border-gray-600 pt-4 flex flex-col md:flex-row justify-around items-center">
        <p>© 2024 Relume. All rights reserved.</p>
        <div class="flex space-x-4">
          <a to="/" class="hover:underline">Privacy Policy</a>
          <a to="/" class="hover:underline">Terms of Service</a>
          <a to="/" class="hover:underline">Cookies Settings</a>
        </div>
      </div>
    </footer>
  </template>
  