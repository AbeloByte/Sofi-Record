<template>
  <section
    id="testimonials"
    class="relative overflow-hidden py-16 bg-[#14141E]"
  >
    <div class="lg:w-[80%] mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-8">
        <span class="text-[#FF3600]">Peoples</span> Feedback
      </h2>
      <!-- Swiper component for automatic sliding -->
      <swiper
        :slides-per-view="2"
        :space-between="10"
        loop
        :autoplay="{ delay: 3000, disableOnInteraction: false }"
        speed="500"
      >
        <!-- Testimonial 1 -->
        <swiper-slide>
          <div class="testimonial-card">
            <img
              src="../public/AbrhamWolde.jpeg"
              alt="Testimonial 1"
              class="testimonial-img"
            />
            <p class="text-xl text-[#fff] mb-2 text-center">
              My experience with this man has been exceptional.
            </p>
            <p class="text-lg font-bold text-[#fff]">Abraham Wolde</p>
            <p class="text-gray-300">Director/Producer · Balageru Records</p>
          </div>
        </swiper-slide>

        <!-- Testimonial 2 -->
        <swiper-slide>
          <div class="testimonial-card">
            <img
              src="../public/Person1.jpeg"
              alt="Testimonial 2"
              class="testimonial-img"
            />
            <p class="text-xl text-[#fff] mb-2 text-center">
              It has been amazing working with this talented person.
            </p>
            <p class="text-lg font-bold text-[#fff]">Eden Taye</p>
            <p class="text-gray-300">Singer/Producer · ETV</p>
          </div>
        </swiper-slide>

        <!-- Testimonial 3 -->
        <swiper-slide>
          <div class="testimonial-card">
            <img
              src="../public/Personal2.jpg"
              alt="Testimonial 3"
              class="testimonial-img"
            />
            <p class="text-xl text-white mb-2 text-center">
              Highly professional and extremely talented!
            </p>
            <p class="text-lg font-bold text-white">Bethel Biruk</p>
            <p class="text-gray-300">Songwriter/Composer · Sofi Records</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </section>
</template>

<script setup>
  import { Swiper, SwiperSlide } from "swiper/vue";
  import "swiper/swiper-bundle.css";
</script>

<style scoped>
.testimonial-card {
  background-color: #14141e;
  padding: 2rem;
  border-radius: 0.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.testimonial-img {
  width: 6rem;
  height: 6rem;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 1rem;
}
</style>
