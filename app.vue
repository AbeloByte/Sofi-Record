<template>
  <div class="bg-[#14141E]">
    <!-- Loader -->
    <Loader class="" v-if="isLoading" />
    <div v-else>
      <NuxtLayout>
        <NuxtLoadingIndicator />
        <NuxtPage />
      </NuxtLayout>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const isLoading = ref(true); // Start with loading state

onMounted(() => {
  // Simulate a data fetch
  setTimeout(() => {
    isLoading.value = false; // Hide loader after 3 seconds
  }, 9000);
});
</script>
