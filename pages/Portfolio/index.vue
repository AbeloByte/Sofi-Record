<template>
  <section class="bg-gray-900 text-white py-16">
    <div class="container mx-auto px-6">
      <h1 class="text-4xl font-bold mb-4 text-center">My Projects</h1>
      <p class="text-center mb-8 max-w-xl mx-auto">
        A showcase of projects. Click on any project to learn more and watch the
        demo video.
      </p>
      <!-- Project Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <NuxtLink
          v-for="project in projects"
          :key="project.id"
          :to="`/Portfolio/${project.id}`"
          class="bg-gray-800 rounded-lg h-48 flex items-center justify-center relative overflow-hidden hover:bg-gray-700 transition-colors duration-200"
        >
          <p class="relative z-10 text-white text-lg font-semibold">
            {{ project.title }}
          </p>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  { id: 1, title: "Project 1", videoId: "video1" },
  { id: 2, title: "Project 2", videoId: "video2" },
  { id: 3, title: "Project 3", videoId: "video3" },
];
</script>
