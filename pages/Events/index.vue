<template>
  <section class="bg-gray-900 min-h-screen p-6">
    <!-- Header Section with Background Image -->
    <div class="relative h-[400px]">
      <img
        src="/MusicEvent.jpg"
        alt="Sheger Concert Stage"
        class="w-full h-full object-cover"
      />
      <div
        class="absolute inset-0 bg-black opacity-40 flex items-center justify-center"
      ></div>
      <div class="absolute inset-0 flex items-center justify-center">
        <h1 class="text-white text-5xl font-bold">{{ eventDetails.title }}</h1>
      </div>
    </div>

    <!-- Content Section with Event Details -->
    <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-6 mt-10">
      <!-- Left Side: Poster Image and Description -->
      <div class="col-span-2 space-y-6">
        <!-- Event Poster -->
        <div class="w-full rounded-lg overflow-hidden">
          <img :src="eventDetails.posterImage" alt="Concert Poster" class="w-full h-auto rounded-lg shadow-lg" />
        </div>

        <!-- Event Description Card -->
        <div class="bg-gray-800 text-white p-6 rounded-lg shadow-lg">
          <p class="leading-relaxed text-lg">{{ eventDetails.description }}</p>
        </div>
      </div>

      <!-- Right Side: Event Details Card -->
      <div class="bg-gray-800 text-white p-6 rounded-lg shadow-lg">
        <h2 class="text-2xl font-semibold text-orange-500 mb-4">Event Details</h2>
        <ul class="space-y-4">
          <li>
            <span class="font-bold">Start Date:</span>
            <span>{{ eventDetails.startDate }}</span>
            <hr class="bg-orange-700 h-1"/>
          </li>
          <li>
            <span class="font-bold">End Date:</span>
            <br/>
            <br/>
            <span>{{ eventDetails.endDate }}</span>
            <hr class="bg-orange-700 h-1"/>
          </li>
          <li>
            <span class="font-bold">Door Time:</span>
            <br/>
            <br/>
            
            <span>{{ eventDetails.doorTime }}</span>
            <hr class="bg-red-400"/>
          </li>
          <li>
            <span class="font-bold">Location:</span>
            <span>{{ eventDetails.location }}</span>
            <hr class="bg-red-400"/>
          </li>
          <li>
            <span class="font-bold">Price:</span>
            <span>{{ eventDetails.price }}</span>
            <hr class="bg-red-400"/>
          </li>
          <li>
            <span class="font-bold">Phone Number:</span>
            <span>{{ eventDetails.phoneNumber }}</span>
            <hr class="bg-red-400"/>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>

import { ref, onMounted } from 'vue';

// to Define the reactive state for event details using `ref`
const eventDetails = ref({
  title: 'SHEGER CONCERT',
  posterImage: '/MusicEvent.jpg', 
  description: `Experience an unforgettable evening at the Sheger Concert, a celebration of Ethiopian music and culture. Set to take place on January 30, 2024, this event will feature a diverse lineup of talented artists, each bringing their unique style to the stage. Don't miss out on this chance to enjoy live performances and vibrant cultural expressions.`,
  startDate: 'January 30, 2024 6:00 PM',
  endDate: 'March 30, 2024 6:00 PM',
  doorTime: '6:00 PM',
  location: 'Megenagna',
  price: '200 Br',
  phoneNumber: '+251987654321',
});

// You can simulate fetching data by using `onMounted`
onMounted(() => {
  // Mock fetching data from an API (you can later replace this part with an actual API call)
  console.log('Event data loaded:', eventDetails.value);
});
</script>

<style scoped>

</style>
