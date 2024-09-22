<template>
  <div class="space-y-8">
    <HeroSection />
    <ServiceandAbout />
    <Clients />
    <Portfolio />
    <TestimonialSection />

    <div class="lg:w-[86%] md:w-[95%] w-[97%] mx-auto">
      <section id="blog" class="latest-blog py-16 lg:mx-14">
        <div class="lg:w-[86%] md:w-[95%] w-[97%] mx-auto">
          <h2 class="text-3xl font-bold text-center mb-8">
            Latest <span class="text-[#FF3600]">Blog</span> Posts
          </h2>
          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Blog Card 1-->

            <NuxtLink
              to="/blog/1"
              class="bg-white p-6 rounded-lg shadow-md flex flex-col hover:shadow-lg transition-shadow duration-300"
              aria-label="Read More about Blog Title"
            >
              <div class="bg-white p-6 rounded-lg shadow-md flex flex-col">
                <img
                  src="../public/photoOne.png"
                  alt="Blog Post"
                  class="w-full h-48 object-cover mb-4 rounded"
                />
                <div class="flex-grow">
                  <h3 class="text-xl font-bold mb-2 text-[#FF3600]">
                    Blog Title
                  </h3>
                  <p class="text-gray-600 mb-4">
                    This is a short paragraph about the blog post. It gives a
                    brief overview or a teaser of the content to entice readers
                    to click and read more.
                  </p>
                  <div class="text-[#FF3600] font-semibold text-sm">
                    Date | 5 min read
                  </div>
                </div>
              </div>
            </NuxtLink>

            <!-- Blog Card 2-->

            <NuxtLink
              href="/blog/[id]"
              class="bg-white p-6 rounded-lg shadow-md flex flex-col hover:shadow-lg transition-shadow duration-300"
              aria-label="Read More about Blog Title"
            >
              <div class="bg-white p-6 rounded-lg shadow-md flex flex-col">
                <img
                  src="../public/PhotoTwo.png"
                  alt="Blog Post"
                  class="w-full h-48 object-cover mb-4 rounded"
                />
                <div class="flex-grow">
                  <h3 class="text-xl font-bold mb-2 text-[#FF3600]">
                    Blog Title
                  </h3>
                  <p class="text-gray-600 mb-4">
                    This is a short paragraph about the blog post. It gives a
                    brief overview or a teaser of the content to entice readers
                    to click and read more.
                  </p>
                  <div class="text-[#FF3600] font-semibold text-sm">
                    Date | 5 min read
                  </div>
                </div>
              </div>
            </NuxtLink>

            <!-- Blog Card 3-->

            <NuxtLink
              href="/blog/[id]"
              class="bg-white p-6 rounded-lg shadow-md flex flex-col hover:shadow-lg transition-shadow duration-300"
              aria-label="Read More about Blog Title"
            >
              <div class="bg-white p-6 rounded-lg shadow-md flex flex-col">
                <img
                  src="../public/PhotoTHree.png"
                  alt="Blog Post"
                  class="w-full h-48 object-cover mb-4 rounded"
                />
                <div class="flex-grow">
                  <h3 class="text-xl font-bold mb-2 text-[#FF3600]">
                    Blog Title
                  </h3>
                  <p class="text-gray-600 mb-4">
                    This is a short paragraph about the blog post. It gives a
                    brief overview or a teaser of the content to entice readers
                    to click and read more.
                  </p>
                  <div class="text-[#FF3600] font-semibold text-sm">
                    Date | 5 min read
                  </div>
                </div>
              </div>
            </NuxtLink>
          </div>
          <!-- Subscribe Blog Button -->
        </div>
      </section>
      <UpcomingEvents />
    </div>
    <Awards />

  </div>
</template>

<script setup>
import { useRouter } from "vue-router";

const router = useRouter();

const gotoEventPage = () => {
  router.push("/Events");
};

useHead({
  title: "Sofi-Records",
  meta: [
    { name: "description", content: "Sofi-Records" },
    { name: "keywords", content: "Sofi-Records" },
  ],
});
</script>

<style scoped></style>
