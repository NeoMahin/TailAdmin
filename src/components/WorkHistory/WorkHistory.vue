<script setup>
import LinkBtn from '../Buttons/LinkBtn.vue';

const sections = [
  {
    title: 'Title of section 1',
    subtitle: 'Sub-Title of section 1',
    content: 'Dolor sit amet, consectetur adipisicing elit. Iusto, optio, dolorum provident rerum aut hic quasi placeat iure tempora laudantium ipsa ad debitis unde? Iste voluptatibus minus veritatis qui ut.',
    dateRange: 'Jan 2018 - May 2020',
    buttonText: 'Diplome'
  },
  {
    title: 'Title of section 2',
    subtitle: 'Sub-Title of section 2',
    content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iure, tempora, laudantium ipsa ad debitis unde? Iste voluptatibus minus veritatis qui ut.',
    dateRange: 'Sep 2020 - Dec 2022',
    buttonText: 'Certificate'
  },
  {
    title: 'Title of section 3',
    subtitle: 'Sub-Title of section 3',
    content: 'Consectetur adipisicing elit. Excepturi, obcaecati, quisquam id molestias eaque asperiores voluptatibus cupiditate error assumenda delectus odit similique earum voluptatem doloremque dolorem ipsam quae rerum quis. Odit, itaque, deserunt corporis vero ipsum nisi eius odio natus ullam provident pariatur temporibus quia eos repellat consequuntur perferendis enim amet quae quasi repudiandae sed quod veniam dolore possimus rem voluptatum eveniet eligendi quis fugiat aliquam sunt similique aut adipisci.',
    dateRange: 'Jan 2023 - Present',
    buttonText: 'Degree'
  },
  {
    title: 'Title of section 4',
    subtitle: 'Sub-Title of section 4',
    content: 'Aut hic quasi placeat iure tempora laudantium ipsa ad debitis unde? Iste voluptatibus minus veritatis qui ut.',
    dateRange: 'May 2024 - Jul 2024',
    buttonText: 'Award'
  }
];
</script>


<template>
    <div class=" lg:pl-7 w-full md:w-1/2">
        <h2 class="text-lg font-semibold text-white pt-0 md:pt-7 pb-7 text-center lg:text-left">Work History</h2>
        <div v-for="(section, index) in sections" :key="index" class="border-r-4 md:pl-7 lg:pl-0 border-black pr-7 group relative pb-7">
          <div class="bg-[#252532] py-7  shadow-lg overflow-hidden">
            <div class="group-hover:animate-ping h-3 w-3 absolute -right-2 top-4.5 rounded-full bg-white opacity-100"></div>
            <div class="px-7">
              <div class="flex flex-wrap justify-between">
                <h2 class="text-white font-semibold text-sm">{{ section.title }}</h2>
                <p class="bg-[#191923] text-xs my-2 py-1 px-2 rounded-2xl w-fit">{{ section.dateRange }}</p>
              </div>
              <div>
                <h2 class="text-white text-sm font-medium">{{ section.subtitle }}</h2>
                <p class="text-[14px] text-white pt-3">{{ section.content }}</p>
              </div>
              <link-btn class="mt-3" :buttonText="section.buttonText" />
            </div>
          </div>
          <div class="bg-[#252532] top-2 -rotate-45 right-6 -z-50 w-8 h-8 absolute"></div>
          <div class="absolute top-4 -right-2.5 border-2 border-yellow-500 rounded-full w-4 h-4">
            <div class="bg-black rounded-full w-3 h-3"></div>
          </div>
        </div>
    </div>
  </template>
  