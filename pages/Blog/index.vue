<template>
  <div>
    <div class="p-4 bg-custom-black lg:px-48">
      <div class="flex justify-center">
        <img
          src="/public/image.png"
          alt="My Image"
          class="m-4 w-full h-auto "
        />
      </div>

      
      <div class="text-white lg:py-8 ">
        <!-- Adjusted from px-44 to px-12 lg:px-48 -->
        <h1 class="text-3xl font-semibold text-primary py-2">Category</h1>
        <h1 class="text-3xl font-semibold py-1">Author : Sultan Nuri</h1>
        <h1 class="text-3xl font-semibold py-3 text-primary">Traditional Tone</h1>
        <h1 class="text-3xl font-semibold">
          How Sofi Records is Redefining Ethiopian Music
        </h1>

        <div class="container mx-auto m-4">
          <hr class="border-t-2 border-white my-4 py-1" />
        </div>

        <div class="flex flex-wrap  text-white text-2xl">
          <p class="text-2xl">
            Introduction: A New Era for Ethiopian Music Sofi Records has always
            been more than just a music label. We see ourselves as curators of
            culture, innovators in sound, and storytellers of Ethiopian
            heritage. In this blog post, we’re excited to share how we’re
            redefining the landscape of Ethiopian music with our latest
            endeavors. Join us as we explore the creative processes,
            collaborations, and innovations that make Sofi Records a leader in
            the industry.
          </p>
        </div>

        <h1 class="text-3xl font-semibold py-4 text-white">
          Preserving Tradition While Embracing Innovation
        </h1>

        <div class="text-white">
          <p class="text-2xl">
            At the heart of Sofi Records lies a deep respect for the rich
            musical traditions of Ethiopia. Our founder, Sofi, has always
            believed that to move forward, we must also look back. This
            philosophy has guided our approach to music production, where we
            strive to preserve the essence of Ethiopian sounds while introducing
            fresh, contemporary elements. Our latest project embodies this
            vision. It’s not just about creating music; it’s about crafting a
            narrative that honors the past while pushing the boundaries of
            what’s possible. Through this project, we aim to showcase the
            versatility of Ethiopian music and its ability to adapt and thrive
            in the modern world.
          </p>
        </div>
      </div>
      <div class="flex justify-center py-4 px-4">
        <button
          class="bg-primary font-semibold text-white px-14 py-3 rounded-full hover:bg-white hover:text-black border border-red-500 text-xl"
        >
          Share
        </button>
      </div>
    </div>

    <div class="bg-custom-white px-12">
      <!-- Matching the blog text's margins -->
      <h1 class="text-4xl font-semibold text-black lg:px-36 py-4">
        Leave <span class="text-primary"> A Comment</span>
      </h1>

      <form @submit.prevent="validateForm" class="bg-custom-white p-6 mx-20">
        <div class="flex flex-row">
          <div class="mb-4 px-10 w-1/2">
            <input
              v-model="firstName"
              class="shadow appearance-none border rounded-2xl w-full py-2 px-3 bg-custom-gray text-3xl text-gray-900 leading-tight focus:outline-none focus:shadow-outline"
              id="first-name"
              type="text"
              placeholder="First Name"
            />
            <p v-if="firstNameError" class="text-red-500 text-xs italic">
              {{ firstNameError }}
            </p>
          </div>

          <div class="mb-4 px-10 w-1/2">
            <input
              v-model="lastName"
              class="shadow appearance-none border rounded-2xl w-full py-2 px-3 bg-custom-gray text-3xl text-gray-900 leading-tight focus:outline-none focus:shadow-outline"
              id="last-name"
              type="text"
              placeholder="Last Name"
            />
            <p v-if="lastNameError" class="text-red-500 text-xs italic">
              {{ lastNameError }}
            </p>
          </div>
        </div>

        <div class="mb-4 px-10">
          <input
            v-model="email"
            class="rounded-2xl shadow appearance-none border w-full py-2 px-3 bg-custom-gray text-3xl text-gray-900 leading-tight focus:outline-none focus:shadow-outline"
            id="email"
            type="email"
            placeholder="Email"
          />
          <p v-if="emailError" class="text-red-500 text-xs italic">
            {{ emailError }}
          </p>
        </div>

        <div class="mb-4 px-10">
          <textarea
            v-model="message"
            class="shadow appearance-none border rounded-2xl w-full py-2 px-3 text-gray-900 text-3xl bg-custom-gray leading-tight focus:outline-none focus:shadow-outline"
            id="message"
            placeholder="Write your comment here..."
            rows="4"
          ></textarea>
          <p v-if="messageError" class="text-red-500 text-xs italic">
            {{ messageError }}
          </p>
        </div>

        <div class="flex items-center justify-between px-10">
          <button
            class="bg-primary text-white px-14 py-3 rounded-full hover:bg-white hover:text-black border border-red-500 text-xl font-semibold"
            type="submit"
          >
            Post Comment
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: "",
      lastName: "",
      email: "",
      message: "",
      firstNameError: "",
      lastNameError: "",
      emailError: "",
      messageError: "",
    };
  },
  methods: {
    validateForm() {
      this.firstNameError = "";
      this.lastNameError = "";
      this.emailError = "";
      this.messageError = "";

      if (!this.firstName) {
        this.firstNameError = "First name is required.";
      }

      if (!this.lastName) {
        this.lastNameError = "Last name is required.";
      }

      const emailPattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
      if (!this.email) {
        this.emailError = "Email is required.";
      } else if (!emailPattern.test(this.email)) {
        this.emailError = "Invalid email format.";
      }

      if (!this.message) {
        this.messageError = "Message is required.";
      }

      if (
        !this.firstNameError &&
        !this.lastNameError &&
        !this.emailError &&
        !this.messageError
      ) {
        alert("Comment submitted successfully!");
      }
    },
  },
};
</script>

<style scoped>
/* Custom styling */
</style>
