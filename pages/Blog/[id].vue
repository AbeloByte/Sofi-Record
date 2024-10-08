<template>
  <div class="p-4 bg-custom-black lg:px-48">
    <div class="flex justify-center">
      <img :src="blog.imgUrl" alt="Blog Image" class="m-4 w-full h-auto" />
    </div>

    <div class="text-white lg:py-8">
      <h1 class="text-3xl font-semibold text-[#FF3600] py-2">
        {{ blog.category }}
      </h1>
      <h1 class="text-xl font-semibold py-1">Author: {{ blog.author }}</h1>
      <h1 class="text-2xl font-semibold py-3 text-[#FF3600]">
        {{ blog.title }}
      </h1>
      <h1 class="text-2xl font-semibold">{{ blog.subtitle }}</h1>

      <div class="container mx-auto m-4">
        <hr class="border-t-2 border-[#FF3600] my-4 py-1" />
      </div>

      <div class="flex flex-wrap text-white text-2xl">
        <p class="text-xl">{{ blog.content }}</p>
      </div>

      <h1 class="text-2xl font-semibold py-4 text-white">
        Preserving Tradition While Embracing Innovation
        <hr class="border-t-2 border-[#FF3600] my-4 py-1" />
      </h1>

      <div class="text-white">
        <p class="text-xl">{{ blog.innovationContent }}</p>
      </div>
    </div>

    <div class="flex justify-end py-4 px-4">
      <button
        class="bg-[#FF3600] font-semibold text-white px-14 py-3 rounded-full hover:bg-white hover:text-black border border-red-500 text-xl"
      >
        Share
      </button>
    </div>
  </div>
  <div class="bg-[#D9D9D9] w-full max-w-4xl mx-auto my-4 p-4">
    <h1 class="text-4xl font-semibold text-black lg:px-36 py-4">
      Leave <span class="text-[#FF3600]"> A Comment</span>
    </h1>

    <form @submit.prevent="validateForm" class="bg-custom-white p-6">
      <div class="flex flex-col md:flex-row gap-4">
        <div class="mb-4 flex-1">
          <input
            v-model="firstName"
            class="shadow appearance-none border rounded w-full py-2 px-3 bg-custom-gray text-xl text-gray-900 leading-tight focus:outline-none focus:shadow-outline"
            id="first-name"
            type="text"
            placeholder="First Name"
          />
          <p v-if="firstNameError" class="text-red-500 text-xs italic mt-1">
            {{ firstNameError }}
          </p>
        </div>

        <div class="mb-4 flex-1">
          <input
            v-model="lastName"
            class="shadow appearance-none border rounded w-full py-2 px-3 bg-custom-gray text-xl text-gray-900 leading-tight focus:outline-none focus:shadow-outline"
            id="last-name"
            type="text"
            placeholder="Last Name"
          />
          <p v-if="lastNameError" class="text-red-500 text-xs italic mt-1">
            {{ lastNameError }}
          </p>
        </div>
      </div>

      <div class="mb-4">
        <input
          v-model="email"
          class="rounded shadow appearance-none border w-full py-2 px-3 bg-custom-gray text-xl text-gray-900 leading-tight focus:outline-none focus:shadow-outline"
          id="email"
          type="email"
          placeholder="Email"
        />
        <p v-if="emailError" class="text-red-500 text-xs italic mt-1">
          {{ emailError }}
        </p>
      </div>

      <div class="mb-4">
        <textarea
          v-model="message"
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-900 text-xl bg-custom-gray leading-tight focus:outline-none focus:shadow-outline"
          id="message"
          placeholder="Write your comment here..."
          rows="4"
        ></textarea>
        <p v-if="messageError" class="text-red-500 text-xs italic mt-1">
          {{ messageError }}
        </p>
      </div>

      <div class="flex items-center justify-center">
        <button
          class="bg-[#FF3600] text-white px-6 py-3 rounded-full hover:bg-white hover:text-black border border-red-500 font-semibold text-xl"
          type="submit"
        >
          Post Comment
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { useRoute } from "vue-router";

// Simulated blog data - replace with real data or API call
const blogs = [
  {
    id: 1,
    category: "Category",
    author: "Sultan Nuri",
    title: "Traditional Tone",
    subtitle: "How Sofi Records is Redefining Ethiopian Music",
    imgUrl: "/MusicProducer.jpg",
    content:
      "Introduction: A New Era for Ethiopian Music Sofi Records has always been more than just a music label. We see ourselves as curators of culture, innovators in sound, and storytellers of Ethiopian heritage. In this blog post, we’re excited to share how we’re redefining the landscape of Ethiopian music with our latest endeavors. Join us as we explore the creative processes, collaborations, and innovations that make Sofi Records a leader in the industry.",
    innovationContent:
      "At the heart of Sofi Records lies a deep respect for the rich musical traditions of Ethiopia. Our founder, Sofi, has always believed that to move forward, we must also look back. This philosophy has guided our approach to music production, where we strive to preserve the essence of Ethiopian sounds while introducing fresh, contemporary elements. Our latest project embodies this vision. It’s not just about creating music; it’s about crafting a narrative that honors the past while pushing the boundaries of what’s possible. Through this project, we aim to showcase the versatility of Ethiopian music and its ability to adapt and thrive in the modern world.",
  },
  // Add more blog entries to simulate dynamic loading
];

const route = useRoute();
const blogId = parseInt(route.params.id, 10);
const blog = ref({});

// Fetch blog data based on the ID from route
onMounted(() => {
  blog.value = blogs.find((blog) => blog.id === blogId) || {};
});

const firstName = ref("");
const lastName = ref("");
const email = ref("");
const message = ref("");

const firstNameError = ref("");
const lastNameError = ref("");
const emailError = ref("");
const messageError = ref("");

function validateForm() {
  firstNameError.value = "";
  lastNameError.value = "";
  emailError.value = "";
  messageError.value = "";

  if (!firstName.value) {
    firstNameError.value = "First name is required.";
  }

  if (!lastName.value) {
    lastNameError.value = "Last name is required.";
  }

  const emailPattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
  if (!email.value) {
    emailError.value = "Email is required.";
  } else if (!emailPattern.test(email.value)) {
    emailError.value = "Invalid email format.";
  }

  if (!message.value) {
    messageError.value = "Message is required.";
  }

  if (
    !firstNameError.value &&
    !lastNameError.value &&
    !emailError.value &&
    !messageError.value
  ) {
    alert("Comment submitted successfully!");
  }
}
</script>

<style scoped>
/* Add any additional styles if necessary */
</style>
