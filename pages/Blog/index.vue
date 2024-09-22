<template>
  <div class="p-4 lg:px-48 mt-24">
    <!-- Grid layout for 4 columns and 4 rows (16 items per page) -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
      <div
        v-for="(post, index) in paginatedBlogs"
        :key="index"
        class="card border rounded-lg p-4 bg-[#f9f9f9] shadow-lg transform transition-transform duration-300 hover:scale-105 w-[500px]" 
      >
        <!-- Blog Image -->
        <img :src="post.imgUrl" alt="Blog Image" class="w-full h-48 object-cover rounded-lg mb-4" />

        <!-- Blog Title -->
        <h2 class="text-xl font-bold text-gray-900 mb-2">{{ post.title }}</h2>

        <!-- Blog Excerpt (Short Paragraph) -->
        <p class="text-gray-700 mb-3">This is a short paragraph about the blog post. It gives a brief overview.</p>

        <!-- Date and Read Time -->
        <div class="text-gray-600 text-sm mb-2">
          <span>{{ post.date }}</span> | <span>{{ post.readTime }} min read</span>
        </div>

        <!-- Number of Comments -->
        <div class="text-gray-600 text-sm mb-4">
          <span>{{ post.comments }} comments</span>
        </div>

        <!-- Button -->
        <nuxt-link :to="`/blog/${post.id}`">
          <button
            class="bg-[#FF3600] text-white px-4 py-2 rounded-full hover:bg-white hover:text-black border border-red-500 w-34"
          >
            See More
          </button>
        </nuxt-link>
      </div>
    </div>

    <!-- Pagination Controls -->
    <div v-if="totalPages > 1" class="flex justify-center mt-8 space-x-4">
      <button
        class="bg-[#FF3600] text-white px-6 py-2 rounded-full hover:bg-white hover:text-black border border-red-500"
        @click="prevPage"
        :disabled="currentPage === 1"
      >
        Previous
      </button>

      <span class="text-white text-lg">{{ currentPage }} / {{ totalPages }}</span>

      <button
        class="bg-[#FF3600] text-white px-6 py-2 rounded-full hover:bg-white hover:text-black border border-red-500"
        @click="nextPage"
        :disabled="currentPage === totalPages"
      >
        Next
      </button>
    </div>
  </div>
</template>



<script setup>
import { ref, computed } from 'vue';

// Example blog data with comments
const blogs = [
  { id: 1, title: 'Traditional Tone', date: 'Jan 1, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 12 },
  { id: 2, title: 'Sofia', date: 'Feb 5, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 8 },
  { id: 3, title: 'Musical Innovations', date: 'Mar 10, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 6 },
  { id: 4, title: 'New Year', date: 'Apr 20, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 14 },
  { id: 5, title: 'Exploring Sounds', date: 'May 11, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 9 },
  { id: 6, title: 'Melody Journey', date: 'Jun 30, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 3 },
  { id: 7, title: 'Ethiopian Rhythms', date: 'Jul 8, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 10 },
  { id: 8, title: 'Cultural Beats', date: 'Aug 15, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 7 },
  { id: 9, title: 'Sofia Sounds', date: 'Sep 18, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 4 },
  { id: 10, title: 'Melodic Vibes', date: 'Oct 21, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 5 },
  { id: 11, title: 'Global Rhythms', date: 'Nov 25, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 13 },
  { id: 12, title: 'Fusion Music', date: 'Dec 30, 2024', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 11 },
  { id: 13, title: 'Innovative Sounds', date: 'Jan 2, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 2 },
  { id: 14, title: 'Ethiopian Culture', date: 'Feb 7, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 15 },
  { id: 15, title: 'Sounds of Africa', date: 'Mar 12, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 18 },
  { id: 16, title: 'Beats and Rhythms', date: 'Apr 22, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 1 },
  { id: 17, title: 'Modern Ethiopian Music', date: 'May 18, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 9 },
  { id: 18, title: 'Music of the World', date: 'Jun 26, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 17 },
  { id: 19, title: 'Rhythms of Asia', date: 'Jul 3, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 19 },
  { id: 20, title: 'Global Music', date: 'Aug 10, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 20 },
  { id: 21, title: 'Music of Africa', date: 'Sep 14, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 16 },
  { id: 22, title: 'Soothing Music', date: 'Oct 17, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 12 },
  { id: 23, title: 'Ethiopian Rhythms', date: 'Nov 22, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 8 },
  { id: 24, title: 'Cultural Music', date: 'Dec 27, 2025', readTime: 5, imgUrl: '/MusicProducer.jpg', comments: 6 },
];

// Pagination settings
const itemsPerPage = 16; // 4 columns x 4 rows = 16 items per page
const currentPage = ref(1);

// Calculate total pages
const totalPages = computed(() => Math.ceil(blogs.length / itemsPerPage));

// Get the blogs for the current page
const paginatedBlogs = computed(() => {
  const start = (currentPage.value - 1) * itemsPerPage;
  const end = start + itemsPerPage;
  return blogs.slice(start, end);
});

// Pagination functions
function prevPage() {
  if (currentPage.value > 1) {
    currentPage.value -= 1;
  }
}

function nextPage() {
  if (currentPage.value < totalPages.value) {
    currentPage.value += 1;
  }
}
</script>




<style scoped>
.card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  max-width: 100%;
  background-color: #f9f9f9;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.shadow-lg {
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}

.rounded-lg {
  border-radius: 10px;
}

button.w-full {
  width: 100%;
  
}

.bg-custom-black {
  background-color: #1b1b1b;
}
</style>

