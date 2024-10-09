<template>
  <header class="bg-neutral-600 text-white w-full h-24">
    <div class="hidden lg:flex justify-around items-center w-full h-full">
      <div>
        <button class="bg-neutral-400 px-14 py-5 text-4xl font-bold">LOGO</button>
      </div>

      <div class="xl:text-xl 2xl:text-2xl">
        <button @click="scrollToSection('home')" class="mr-4 2xl:mr-8">HOME</button>
        <button @click="scrollToSection('HTP')" class="mr-4 2xl:mx-8">COMO PARTICIPAR</button>
        <button @click="scrollToSection('prizes')" class="mr-4 2xl:mx-8">PRÊMIOS</button>
        <button @click="scrollToSection('FAQs')" class="mr-4 2xl:mx-8">DÚVIDAS FREQUENTES</button>
        <button @click="scrollToSection('winners')" class="mr-4 2xl:ml-8">GANHADORES</button>
      </div>

      <button class="flex justify-around font-bold text-lg xl:text-xl 2xl:text-2xl xl:gap-4">
        <img
          src="../assets/user-icon.png"
          alt="Ícone"
          class="w-8 h-8"
        />
        <h1>LOGIN/CADASTRAR</h1>
      </button>
    </div>

    <!-- Menu Burguer para telas menores -->
    <div class="lg:hidden flex justify-between items-center px-4">
      <button class="bg-neutral-400 px-10 py-4 text-2xl font-bold my-2">LOGO</button>
      <MenuBurguer/>
    </div>
  </header>
</template>

<script>
import MenuBurguer from './MenuBurguer.vue'

export default {
  name: "Menu",
  components: {
    MenuBurguer
  },
  methods: {
    scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>
