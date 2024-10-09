<template class="min-h-screen">

  <Menu/>
  <CampaignBanner/>
  <HowToParticipate/>
  <PrizeComponent/>
  <FAQsComponent/>
  <Winners/>
  <FooterComponent/>
  
</template>

<script>
import Menu  from './components/Menu.vue'
import CampaignBanner from"./components/CampaignBanner.vue"
import HowToParticipate from './components/HowToParticipate.vue'
import PrizeComponent from './components/PrizeComponent.vue'
import FAQsComponent from './components/FAQsComponent.vue'
import Winners from './components/Winners.vue'
import FooterComponent from "./components/FooterComponent.vue"


export default {
  name: 'App',
  components: {
    Menu,
    CampaignBanner,
    HowToParticipate,
    PrizeComponent,
    FAQsComponent,
    Winners,
    FooterComponent
  }
}
</script>

