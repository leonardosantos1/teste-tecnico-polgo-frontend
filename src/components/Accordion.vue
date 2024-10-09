<template>
    <div class="mx-auto my-2 w-3/4">
      <div
        class="bg-neutral-500 text-white font-bold py-3 px-4 cursor-pointer rounded-2xl"
        @click="$emit('toggle')"
      >
        <div class="flex justify-between items-center text-2xl">
          {{ title }}
          <svg
            :class="isOpen ? 'transform rotate-180' : 'transform rotate-0'"
            class="w-6 h-6 transition-transform duration-300 ease-in-out"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
          </svg>
        </div>
  
        <transition @enter="enter" @leave="leave">
          <div v-show="isOpen" class="overflow-hidden">
            <div class="mt-2 text-xl font-normal">
              <slot />
            </div>
          </div>
        </transition>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      isOpen: Boolean
    },
    methods: {
      enter(el) {
        el.style.height = 0
        const actualHeight = el.scrollHeight;
        requestAnimationFrame(() => {
          el.style.transition = 'height 0.3s ease'
          el.style.height = actualHeight + 'px'
        });
      },
      leave(el) {
        el.style.height = el.scrollHeight + 'px'
        requestAnimationFrame(() => {
          el.style.transition = 'height 0.3s ease'
          el.style.height = 0
        });
      }
    }
  };
  </script>
  
  <style scoped>
  </style>