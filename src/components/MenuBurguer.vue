<template>
  <div>
    <!-- Ícone de menu hamburguer -->
    <button @click="toggleMenu" class="focus:outline-none">
      <svg class="w-12 h-12 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
      </svg>
    </button>

    <!-- Menu dropdown -->
    <transition name="slide-fade" class="my-4">
      <nav v-if="isMenuOpen" class="absolute top-16 right-0 bg-neutral-600 text-white w-full flex flex-col items-center space-y-4 py-4 z-40">
        <button @click="scrollToSection('home')" class="w-full text-center">HOME</button>
        <button @click="scrollToSection('HTP')" class="w-full text-center">COMO PARTICIPAR</button>
        <button @click="scrollToSection('prizes')" class="w-full text-center">PRÊMIOS</button>
        <button @click="scrollToSection('FAQs')" class="w-full text-center">DÚVIDAS FREQUENTES</button>
        <button @click="scrollToSection('winners')" class="w-full text-center">GANHADORES</button>
        <button class="w-full flex justify-center items-center gap-2">
          <img
            src="../assets/user-icon.png"
            alt="Ícone"
            class="w-8 h-8"
          />
          <h1>LOGIN/CADASTRAR</h1>
        </button>
      </nav>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
      this.isMenuOpen = false
    }
  }
}
</script>

<style scoped>
.slide-fade-enter-active, .slide-fade-leave-active {
  transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
}
.slide-fade-enter-from {
  opacity: 0; 
}
.slide-fade-enter-to {
  opacity: 1;
}
.slide-fade-leave-from {
  opacity: 1;
}
.slide-fade-leave-to {
  opacity: 0;
}
</style>
