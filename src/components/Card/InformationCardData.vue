<script setup>
import { ref } from 'vue'
import InformationCard from '../../components/Card/InformationCard.vue'

const data = ref([
  [
    {
      country: 'canada',
      city: 'toronto',
      Streat: '20 dellbank Rd',
    }
  ],

  [{ Email:'carter.inbox@mail.com', Telegram: '@arter', Skype: 'Arter' }],
  [
    {
      service: '+78(098)3331122',
      Office: '+78(098)3261122',
      Personal: '+78(098)3261122'
    }
  ]
])
</script>

<template>
  <section>
    <h2 class="text-lg font-semibold text-white pb-7 pt-14 text-center lg:text-left">Contact information</h2>
  
    <div class="flex flex-col sm:flex-row md:flex-row gap-7">
      <information-card v-for="(item, index) in data" :key="index" :cardData="item" />
    </div>
  </section>
</template>