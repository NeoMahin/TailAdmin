<script setup>
import { onMounted, ref, defineProps, toRefs } from 'vue'

// Define props including `ratingNum`
let props = defineProps({
  title: String,
  subTitle: String,
  des: String,
  imgSrc: String,
  ratingNum: Number // Add ratingNum here
})

const { ratingNum } = toRefs(props);

let ratings = ref([
  { id: 1, isActive: false },
  { id: 2, isActive: false },
  { id: 3, isActive: false },
  { id: 4, isActive: false },
  { id: 5, isActive: false }
])

function handleRating() {
  if (!ratingNum.value) return 
  for (let index = 0; index < ratingNum.value; index++) {
    ratings.value[index].isActive = true
  }
}

onMounted(()=>{
  handleRating()
})

</script>

<template>
  <div class="bg-[#252532] shadow-lg w-full relative">
    <img
      :src="imgSrc"
      alt=""
      class="absolute top-0 mt-2 right-4 h-16 w-16 rounded-full object-cover"
    />
    <div class="p-6">
      <div class="flex justify-between">
        <h3 class="text-base font-semibold text-white">{{ title }}</h3>
      </div>
      <p class="text-sm mb-2 text-white font-medium">{{ subTitle }}</p>
      <p class="text-sm my-4 text-white">{{ des }}</p>
      <ul class="bg-[#191923] py-1 px-2 flex items-center rounded-2xl w-fit">
        <li v-for="rating in ratings" :key="rating.id">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="currentColor"
            class="size-3"
            :class="rating.isActive ? 'text-yellow-500' : ''"
          >
            <path
              fill-rule="evenodd"
              d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.006 5.404.434c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.434 2.082-5.005Z"
              clip-rule="evenodd"
            />
          </svg>
        </li>
      </ul>
    </div>
  </div>
</template>
