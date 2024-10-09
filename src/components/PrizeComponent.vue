<template>
    <section id="prizes" class="grid grid-rows-3 place-items-center w-full">
        <h1 class="font-bold text-4xl xl:text-6xl text-neutral-600 ">PRÊMIOS</h1>
        <CustomCarousel/>
        <div>
            <button class="bg-neutral-500 text-white font-bold py-4 px-28 lg:py-4 lg:px-48 rounded-full xl:text-2xl">
                    CADASTRAR-SE
            </button>
        </div>
    </section>

</template>



<script>
import CustomCarousel from './CustomCarousel.vue'


export default{
    name:"PrizeComponent",
    components:{
        CustomCarousel
    }
}

</script>