<template>
  <div class="relative w-[65%] xl:w-[50%] mx-auto">
    <div class="overflow-hidden">
      <div
        class="flex transition-transform duration-300"
        :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
      >
        <div
          v-for="(slide, index) in slides"
          :key="index"
          class="min-w-full flex-shrink-0 bg-cover bg-center h-64"
          :style="{ backgroundImage: `url(${slide})` }"
        >
        </div>
      </div>
    </div>

    <button
      @click="prevSlide"
      class="absolute top-1/2 left-0 transform -translate-y-1/2 bg-gray-700 text-white p-2 rounded-full"
    >
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
      </svg>
    </button>

    <button
      @click="nextSlide"
      class="absolute top-1/2 right-0 transform -translate-y-1/2 bg-gray-700 text-white p-2 rounded-full"
    >
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
      </svg>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSlide: 0,
      slides: [
        "https://via.placeholder.com/600x400/B7B7B7/FFFFFF?text=Slide+1",
        "https://via.placeholder.com/600x400/B7B7B7/FFFFFF?text=Slide+2",
        "https://via.placeholder.com/600x400/B7B7B7/FFFFFF?text=Slide+3",
        "https://via.placeholder.com/600x400/B7B7B7/FFFFFF?text=Slide+4",
      ],
    };
  },
  methods: {
    nextSlide() {
      if (this.currentSlide < this.slides.length - 1) {
        this.currentSlide++;
      } else {
        this.currentSlide = 0
      }
    },
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      } else {
        this.currentSlide = this.slides.length - 1
      }
    },
  },
};
</script>

