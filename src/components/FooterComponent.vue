<template>

    <div v-if="screenWidth >= 1024" class="bg-neutral-500 flex justify-around w-full h-[21.875rem]">
        <div class="h-full flex flex-col justify-around items-center">
            <div>            
                <button class="bg-white px-14 py-[20px] text-4xl font-bold text-neutral-500">LOGO</button>
            </div>
            <div>
                <img
                src="../assets/grupo-polgo.png"
                alt="Ícone"
                class="w-32 h-10"
                >
            </div>
        </div>
        <div class="h-full flex flex-col items-start justify-center gap-10 text-2xl text-white">
            <h1>Politica de privacidade</h1>
            <h1>Termos de uso</h1>
            <h1>Regulamento</h1>
            <h1>SRE: 000000000000000000</h1>
        </div>
        <div class="h-full flex flex-col gap-3 pt-10 text-xl">
            <div class="grid grid-cols-4 pb-4" >
                <img
                 src="../assets/icons8-facebook.svg"
                alt="Ícone"
                class="w-10 h-10  bg-white"
                />
                <img
                 src="../assets/icons8-instagram.svg"
                alt="Ícone"
                class="w-10 h-10 bg-white"
                />
                <img
                 src="../assets/icons8-linkedin.svg"
                alt="Ícone"
                class="w-10 h-10 bg-white"
                />
                <img
                 src="../assets/icons8-youtube.svg"
                alt="Ícone"
                class="w-10 h-10 bg-white"
                />

            </div>
            <h1 class="text-2xl text-white">HOME</h1>
            <h1 class="text-2xl text-white">COMO PARTICIPAR</h1>
            <h1 class="text-2xl text-white">PRÊMIOS</h1>
            <h1 class="text-2xl text-white">DUVIDAS FREQUENTES</h1>
            <h1 class="text-2xl text-white">GANHADORES</h1>
        </div>
    </div>

    <div v-if="screenWidth < 1024" class="bg-neutral-500 flex flex-col items-center w-full h-full py-8">
            <div>            
                <button class="bg-white px-24 py-[20px] text-4xl font-bold text-neutral-500">LOGO</button>
            </div>
            
        <div class="h-full flex flex-col justify-center gap-10 text-2xl text-white text-center my-4">
            <h1>Politica de privacidade</h1>
            <h1>Termos de uso</h1>
            <h1>Regulamento</h1>
            <h1>SRE: 000000000000000000</h1>
        </div>
        <div class="h-full flex flex-col justify-center  gap-3 pt-10 text-xl text-center my-2">
        
            <h1 class="text-2xl text-white">HOME</h1>
            <h1 class="text-2xl text-white">COMO PARTICIPAR</h1>
            <h1 class="text-2xl text-white">PRÊMIOS</h1>
            <h1 class="text-2xl text-white">DUVIDAS FREQUENTES</h1>
            <h1 class="text-2xl text-white">GANHADORES</h1>
            <div class="flex justiify-between gap-12 py-6" >
                <img
                 src="../assets/icons8-facebook.svg"
                alt="Ícone"
                class="w-10 h-10  bg-white"
                />
                <img
                 src="../assets/icons8-instagram.svg"
                alt="Ícone"
                class="w-10 h-10 bg-white"
                />
                <img
                 src="../assets/icons8-linkedin.svg"
                alt="Ícone"
                class="w-10 h-10 bg-white"
                />
                <img
                 src="../assets/icons8-youtube.svg"
                alt="Ícone"
                class="w-10 h-10 bg-white"
                />

            </div>
        </div>
        <div>
                <img
                src="../assets/grupo-polgo.png"
                alt="Ícone"
                class="w-32 h-10"
                >
            </div>
    </div>

</template>


<script>
    export default{
        name:"FooterComponent",
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