<template>
    <section id="FAQs" class=" bg-neutral-300 flex flex-col items-center w-full h-full pb-28">
      <h1 class="font-bold text-3xl 2xl:text-6xl text-neutral-600 my-12 center">DÚVIDAS FREQUENTES</h1>

      <Accordion
        v-for="(item, index) in accordions"
        :key="index"
        :title="item.title"
        :is-open="openIndex === index"
        @toggle="handleToggle(index)"
      >
        {{ item.content }}
      </Accordion>
    </section>
  </template>
  
  <script>
  import Accordion from './Accordion.vue'
  
  export default {
    name:"FAQsComponent",
    components: { Accordion },
    data() {
      return {
        accordions: [
          { title: '1- Como faço para participar da promoção?', content: 'Basta fazer o cadastro através do site XXXXXXXX. Ao finalizar o cadastro, você receberá um número da sorte.' },
          { title: '2- Quem pode participar da promoção?', content: 'A participação nesta promoção é aberta às pessoas físicas, maiores 18 anos, residentes e domiciliadas em território nacional, que possuírem CPF válido' },
          { title: '3- Qual o período para participar da promoção?', content: 'XX/XX/XXXX a XX/XX/XXXX' },
          { title: '4- Quais as datas do sorteio?', content: 'Sorteio do número da sorte da Loteria Federal: XX/XX/XXXX' },
          { title: '5- Como saberei se fui contemplado?', content: 'Os ganhadores do sorteio do número da sorte serão avisados por meio de ligação telefônica, e-mail e/ou Whatsapp, de acordo com os dados fornecidos no cadastro, mas não necessariamente nesta ordem. Os nomes dos ganhadores serão divulgados em XXXXXXXXX no dia XX/XX/XXXX' },
          { title: '6- Qual o prazo para entrega dos prêmios?', content: 'Os prêmios serão entregues em até 30 dias da data da apuração/sorteio.' },
          { title: '7- Participei fora do período da promoção, poderei concorrer?', content: 'Não, os cadastros realizados fora do período de participação desta Campanha, não serão considerados para fins de premiação' },
          { title: '8- Posso realizar cadastros emm nome de outras pessoas?', content: 'Não, o cadastro de participação deverá ser realizado pelo titular do CPF cadastrado. A divergência das informações do Participante cadastrado poderá acarretar desclassificação, no caso de eventual premiação.' },
          { title: '9- O que acontece se eu não apresentar a documentação?', content: 'A recusa em apresentar documentos que comprovem as exigências para participação na Campanha ou a apresentação de documentos com sinais claros de adulteração ou sem condições de leitura ou verificação, ensejará a desclassificação do Participante.' },
          { title: '10- A campanha vale para todo o território nacional', content: 'Sim, será válida em todo o território nacional durante o período de participação.'}

        ],
        openIndex: null
      }
    },
    methods: {
      handleToggle(index) {
        this.openIndex = this.openIndex === index ? null : index
      }
    }
  };
  </script>