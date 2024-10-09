<template>
    <section id="HTP" class="w-full h-full flex justify-center">
        <div v-if="screenWidth >= 1920" class="bg-neutral-300 grid place-items-center grid-rows-3 w-[320rem] h-[67.5rem] ">
            <h1 class="font-bold text-6xl text-neutral-600">COMO PARTICIPAR</h1>
            <div class="grid grid-cols-4 place-items-center gap-8">
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 1</span>
                </div>
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 2</span>
                </div>
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 3</span>
                </div>
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 4</span>
                </div>
            </div>
            <div> 
                <button class="bg-neutral-500 text-white font-bold py-4 px-48 rounded-full text-2xl">
                    CADASTRAR-SE
                </button>
            </div>
        </div>

        <div v-if="(screenWidth < 1920 && screenWidth >= 1024)" class="bg-neutral-300 grid place-items-center grid-rows-3 w-[320rem] h-[67.5rem] gap-48 ">
            <h1 class="font-bold text-6xl text-neutral-500">COMO PARTICIPAR</h1>
            <div class="grid grid-cols-2 place-items-center gap-8">
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 1</span>
                </div>
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 2</span>
                </div>
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 3</span>
                </div>
                <div class=" flex justify-center items-center bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 4</span>
                </div>
            </div>
            <div> 
                <button class="bg-neutral-500 text-white font-bold py-4 px-48 rounded-full text-2xl">
                    CADASTRAR-SE
                </button>
            </div>
        </div>

        <div v-if="(screenWidth < 1024)" class="bg-neutral-300 flex flex-col items-center justify-center w-[320rem] h-full gap-12 ">
            <h1 class="font-bold text-4xl text-neutral-500 mt-12">COMO PARTICIPAR</h1>
            <div class="flex flex-col gap-4 items-center justify-center">
                <div class="  bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 1</span>
                </div>
                <div class="  bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 2</span>
                </div>
                <div class="  bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 3</span>
                </div>
                <div class="  bg-neutral-500 w-80 h-80 rounded-lg font-bold text-white text-xl">
                    <span >IMAGE 4</span>
                </div>
            </div>
                <button class="bg-neutral-500 text-white font-bold py-4 px-28 rounded-full text-md mb-24">
                    CADASTRAR-SE
                </button>
        </div>
    </section>
    
</template>



<script>

export default{
    name:"HowToParticipate",
    data() {
    return {
      screenWidth: window.innerWidth,
    };
  },
  mounted() {
    window.addEventListener("resize", this.updateScreenWidth)
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.updateScreenWidth)
  },
  methods: {
    updateScreenWidth() {
      this.screenWidth = window.innerWidth
      this.screenHeight = window.innerHeight
    },
  },
}

</script>