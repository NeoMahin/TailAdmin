<script setup>
import { ref, onMounted } from 'vue';


const speed = 2000;


function setupCounter(target) {
  const counter = ref(0);
  const intervalSpeed = speed / target;

  onMounted(() => {
    const interval = setInterval(() => {
      if (counter.value < target) {
        counter.value++;
      } else {
        clearInterval(interval);
      }
    }, intervalSpeed);
  });

  return counter;
}

const experienceNumber = setupCounter(10);
const projectComplete = setupCounter(143); 
const customers = setupCounter(114);
const awards = setupCounter(20);
</script>

<template>
  <section>
    <div class="lg:px-7">
      <div class="flex flex-wrap items-center justify-between">
        <div class="w-1/2 md:w-1/4 flex my-2 md:my-0 items-center pr-2">
          <span class="text-2xl pr-4 text-yellow-500 font-semibold">{{ experienceNumber }}+</span><span class="text-white text-sm font-medium">Years experience</span> 
        </div>
        <div class="w-1/2 md:w-1/4 flex my-2 md:my-0 items-center pr-2">
          <span class="text-2xl pr-6 text-yellow-500 font-semibold">{{ projectComplete }}</span><span class="text-white text-sm font-medium">Completed Projects</span> 
        </div>
        <div class="w-1/2 md:w-1/4 flex my-2 md:my-0 items-center pr-2">
          <span class="text-2xl pr-6 text-yellow-500 font-semibold">{{ customers }}</span><span class="text-white text-sm font-medium">Happy Customers</span>
        </div>
        <div class="w-1/2 md:w-1/4 flex my-2 md:my-0 items-center pr-2">
          <span class="text-2xl pr-4 text-yellow-500 font-semibold">{{ awards }}+</span><span class="text-white text-sm font-medium">Honors and Awards</span>
        </div>
      </div>
    </div>
  </section>
</template>
