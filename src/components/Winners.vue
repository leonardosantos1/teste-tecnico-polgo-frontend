<template>
  <section id="winners" class="flex flex-col items-center w-full h-[62rem] ">
    <h1 class="font-bold text-4xl 2xl:text-6xl text-neutral-600 my-24">GANHADORES</h1>

    <Accordion
      v-for="(item, index) in accordions"
      :key="index"
      :title="item.title"
      :is-open="openIndex === index"
      @toggle="handleToggle(index)"
    >
      <ul>
        <li v-for="winner in item.winners" :key="winner.name" class="my-2 gap-4">
          <p class="my-2"><strong>Nome:</strong> {{ winner.name }}</p>
          <p class="my-2"><strong>Prêmio:</strong> {{ winner.prize }}</p>
          <p class="my-2"><strong>Data:</strong> {{ winner.date }}</p>
          <hr>
        </li>
      </ul>
    </Accordion>
  </section>
</template>

<script>
import axios from 'axios';
import Accordion from './Accordion.vue';

export default {
  name: "Winners",
  components: { Accordion },
  data() {
    return {
      accordions: [
        { title: '1° SORTEIO XX/XX/XX', winners: [] }, 
      ],
      openIndex: null, 
      error: null 
    };
  },
  created() {
    this.fetchWinners()
  },
  methods: {
    
    async fetchWinners() {
      try {
        
        const response = await axios.get('https://teste-tecnico-polgo-landing-page.onrender.com/winners')
        
        
        this.accordions[0].winners = response.data
        console.log(this.accordions[0].winners)
      } catch (error) {
        this.error = 'Erro ao carregar os ganhadores. Tente novamente mais tarde.'
        console.error(error)
      }
    },
    handleToggle(index) {
      this.openIndex = this.openIndex === index ? null : index
    }
  }
};
</script>