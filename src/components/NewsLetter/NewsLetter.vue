<script setup>
import { onMounted, ref, defineProps, toRefs } from 'vue'
import LinkBtn from '../Buttons/LinkBtn.vue';

let props = defineProps({
  title: String,
  subTitle: String,
  des: String,
  imgSrc: String,
})


</script>

<template>
  <div class="bg-[#252532] shadow-lg w-full overflow-hidden relative">
    <div class="w-full lg:w-[343px] h-[207px]">
        <a href=":;">
            <img
              :src="imgSrc"
              alt=""
              class="w-full h-full object-cover"
            />
        </a>
    </div>
    <div class="p-6">
      <div class="">
        <h3 class="text-base font-semibold text-white">{{ title }}</h3>
      </div>
      <p class="text-sm mb-2 text-white font-medium">{{ subTitle }}</p>
      <p class="text-[14px] my-4 text-white">{{ des }}</p>
      <link-btn buttonText="Read more" />
    </div>
  </div>
</template>
