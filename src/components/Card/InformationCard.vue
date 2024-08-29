<script setup>
defineProps({
  cardData: Array
})
  
</script>

<template>
  <div class="bg-[#252532] shadow-lg flex items-center overflow-hidden w-full">
    <div class="w-full">
      <ul class="px-6 py-6" v-if="cardData[0]">

        <li class="flex items-center justify-between" v-for="(item, index) in Object.keys(cardData[0])" :key="index">

            <span class=" text-sm font-medium text-white  pb-1">
              {{ item }}
            </span>
            <span class="text-sm text-white pb-1 text-right">
              {{
                cardData[0][item]
              }}
            </span>
        </li>
      </ul>
    </div>
  </div>
</template>
