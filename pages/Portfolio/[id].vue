<template>
  <section class="bg-[#2A2727] text-gray-900 py-16">
    <div class="container mx-auto px-6 md:w-[80%]">
      <!-- Project Title and Tagline -->
      <div class="text-center mb-12">
        <h1 class="text-5xl font-bold text-gray-800 mb-4">{{ project.title }}</h1>
        <p class="text-xl italic text-gray-500">{{ project.tagline }}</p>
      </div>

      <!-- YouTube Embed -->
      <div class="relative overflow-hidden rounded-lg shadow-lg mb-12" style="padding-bottom: 56.25%; height: 0;">
        <iframe
          class="absolute top-0 left-0 w-full h-full rounded-lg"
          :src="`https://www.youtube.com/embed/${project.videoId}`"
          frameborder="0"
          allowfullscreen
        ></iframe>
      </div>

      <!-- Project Overview -->
      <div class="bg-white rounded-lg shadow-md py-12 px-8 mb-8 transition-transform hover:scale-105">
        <h2 class="text-3xl font-bold mb-6 text-center text-gray-800">Project Overview</h2>
        <p class="text-lg leading-relaxed text-center text-gray-700">{{ project.description }}</p>
      </div>

      <!-- Key Challenges -->
      <div class="bg-gray-50 rounded-lg shadow-md py-12 px-8 mb-8 transition-transform hover:scale-105">
        <h2 class="text-3xl font-bold mb-6 text-center text-gray-800">Key Challenges</h2>
        <p class="text-lg leading-relaxed text-center text-gray-700">{{ project.challenges }}</p>
      </div>

      <!-- Tools and Technologies -->
      <div class="bg-white rounded-lg shadow-md py-12 px-8 mb-8 transition-transform hover:scale-105">
        <h2 class="text-3xl font-bold mb-6 text-center text-gray-800">Tools and Technologies</h2>
        <ul class="list-disc pl-6 space-y-2 text-lg text-center text-gray-700">
          <li v-for="tool in project.tools" :key="tool">{{ tool }}</li>
        </ul>
      </div>

      <!-- Impact and Reception -->
      <div class="bg-gray-50 rounded-lg shadow-md py-12 px-8 mb-8 transition-transform hover:scale-105">
        <h2 class="text-3xl font-bold mb-6 text-center text-gray-800">Impact and Reception</h2>
        <p class="text-lg leading-relaxed text-center text-gray-700">{{ project.impact }}</p>
      </div>

      <!-- Behind the Scenes -->
      <div class="bg-white rounded-lg shadow-md py-12 px-8 mb-8 transition-transform hover:scale-105">
        <h2 class="text-3xl font-bold mb-6 text-center text-gray-800">Behind the Scenes</h2>
        <p class="text-lg leading-relaxed text-center text-gray-700">{{ project.behindTheScenes }}</p>
      </div>

      <!-- Testimonials -->
      <div class="bg-gray-50 rounded-lg shadow-md py-12 px-8 mb-8 transition-transform hover:scale-105">
        <h2 class="text-3xl font-bold mb-6 text-center text-gray-800">Testimonials</h2>
        <blockquote class="italic border-l-4 pl-4 border-orange-500 text-lg text-center text-gray-700">
          "{{ project.testimonial }}"
          <footer class="mt-4 text-gray-600">— {{ project.testimonialAuthor }}</footer>
        </blockquote>
      </div>

      <!-- Call to Action -->
      <div class="text-center py-12">
        <NuxtLink
          class="text-orange-500 hover:underline transition duration-300 ease-in-out text-xl font-semibold"
          to="/projects"
        >
          ← Back to Projects
        </NuxtLink>
        <p class="mt-6 text-lg text-gray-600">
          Want to collaborate or learn more? <NuxtLink class="text-orange-500 hover:underline transition duration-300 ease-in-out" to="/contact">Get in touch.</NuxtLink>
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { useRoute } from 'vue-router';

const route = useRoute();
const projectId = route.params.id;

const projects = [
  {
    id: 1,
    title: 'Project 1: Ethiopian Pop Fusion',
    tagline: 'Blending traditional Ethiopian sounds with modern pop',
    videoId: 'yourYouTubeVideoID1',
    description: 'This project showcases my effort to merge Ethiopian traditional music with modern pop sounds. By carefully balancing these elements, I created something new and fresh while still honoring the past.',
    challenges: 'One of the biggest challenges was balancing the tempo of traditional Ethiopian instruments with modern pop beats. After much experimentation, we were able to create a seamless blend of the two.',
    tools: ['Logic Pro X', 'Roland TR-808', 'Native Instruments Kontakt', 'Vocal processing by XYZ Studio'],
    impact: 'This project was widely acclaimed, receiving over 1 million streams on Spotify and winning "Best Modern Fusion" at the 2023 Ethiopian Music Awards.',
    behindTheScenes: 'The project began with a research trip to the Ethiopian Highlands, where I recorded traditional instruments. Back in the studio, I blended these recordings with digital beats to create the final sound.',
    testimonial: 'This producer is a true visionary, blending modern and traditional elements into a sound that is both familiar and completely new.',
    testimonialAuthor: 'Famous Ethiopian Artist',
  },
  {
    id: 2,
    title: 'Project 2: Traditional Roots Revived',
    tagline: 'Reviving the roots of Ethiopian folk music for a new generation',
    videoId: 'yourYouTubeVideoID2',
    description: 'This project is a revival of Ethiopian folk music, reimagined for a younger audience. I worked with several traditional musicians to preserve the authenticity of the music while adding a modern touch.',
    challenges: 'Staying true to the original while appealing to modern listeners was a delicate balance, but the final product stays true to both.',
    tools: ['Ableton Live', 'Vintage Drum Machine', 'Analog Synths'],
    impact: 'The project was praised by both younger and older generations, proving that folk music can still be relevant today.',
    behindTheScenes: 'I spent months traveling to different regions of Ethiopia, gathering folk songs and learning from local musicians. This project was a true labor of love.',
    testimonial: 'A brilliant re-imagining of our cultural heritage. The younger generation is sure to appreciate this fresh take on Ethiopian folk music.',
    testimonialAuthor: 'Music Historian',
  },
  {
    id: 3,
    title: 'Project 3: Urban Soundscapes',
    tagline: 'An exploration of Ethiopia’s urban musical scene',
    videoId: 'yourYouTubeVideoID3',
    description: 'This project is an exploration of the urban sounds of Ethiopia, combining influences from the streets of Addis Ababa with electronic music.',
    challenges: 'Capturing the energy of the city in a studio setting was tough, but through collaboration with local DJs and producers, we created a sound that is undeniably Addis.',
    tools: ['FL Studio', 'Analog Synths', 'Field Recordings from Addis'],
    impact: 'The track became an underground hit in Addis Ababa and is now played in clubs across the city.',
    behindTheScenes: 'I spent weeks recording sounds from the streets of Addis Ababa, which were later processed and incorporated into the track. The sounds of the city are literally embedded in this project.',
    testimonial: 'A perfect blend of Ethiopia’s rich urban culture with modern production techniques.',
    testimonialAuthor: 'Club DJ',
  },
];

const project = projects.find(p => p.id == projectId);
</script>
