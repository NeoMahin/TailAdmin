<script setup>
import LinkBtn from '../Buttons/LinkBtn.vue';

defineProps({
  title: String,
  des: String,
})

</script>

<template>
  <div class="bg-[#252532] shadow-lg overflow-hidden w-full">
    <div class="p-6">
      <h3 class="text-base font-semibold text-white">{{ title }}</h3>
      <p class="text-[14px] my-4 text-white">{{ des }}</p>

      <link-btn buttonText="Order now" />
    </div>
  </div>
</template>
