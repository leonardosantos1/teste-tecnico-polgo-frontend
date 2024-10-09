<template>

  <section id="home" class="w-full h-full flex justify-center">
      <div v-if="screenWidth >= 1920" class="w-[320rem] h-[67.5rem]">
        <div class="w-full h-[67.5rem] bg-neutral-400 flex justify-center items-center">
            <span class="text-white text-5xl font-bold">BANNER</span>
        </div>
      </div>
        
        
      <div v-if="(screenWidth < 1920 && screenWidth >= 1366) "class="w-[85.375rem] h-[64rem] flex justify-center">
        <div class="w-full h-full bg-neutral-400 flex justify-center items-center">

            <span class="text-white text-5xl font-bold">BANNER</span>

            
        </div>
        
    </div>
     
    <div v-if="(screenWidth < 1366 && screenWidth >= 1024) "class="h-[85.375rem] w-[64rem] flex justify-center">
        <div class="w-full h-full bg-neutral-400 flex justify-center items-center">
            <span class="text-white text-5xl font-bold">BANNER</span>
        </div>
        
    </div>

    <div v-if="screenWidth > 360 && screenWidth < 1024" class="w-[22.5rem] h-[50rem] flex justify-center">
        <div class="w-full h-full bg-neutral-400 flex justify-center items-center">
            <span class="text-white text-5xl font-bold">BANNER</span>
        </div>
    </div>

    
    <div v-if="screenWidth <= 360" class="w-[22.5rem] h-[50rem] flex justify-center">
        <div class="w-[20rem] h-full bg-neutral-400 flex justify-center items-center">
            <span class="text-white text-5xl font-bold">BANNER</span>
        </div>
    </div>
  </section>
   
</template>


<script>


export default{

    name:"CampaignBanner",
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
    },
  },
}

</script>