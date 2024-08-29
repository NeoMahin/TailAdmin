<script setup lang="ts">
import { useSidebarStore } from '@/stores/sidebar'
import { onClickOutside } from '@vueuse/core'
import { ref, onMounted } from 'vue'
import ProgressBar from 'progressbar.js'

interface ProgressBarCircle {
  path: SVGPathElement
  value(): number
  setText(text: string): void
}

const target = ref<HTMLElement | null>(null)
const sidebarStore = useSidebarStore()

onClickOutside(target, () => {
  sidebarStore.isSidebarOpen = false
})

const progressValues = [1.0, 0.9, 0.7]
const labels = ['French', 'English', 'Spanish']


onMounted(() => {
  progressValues.forEach((value, index) => {
    const container = (target.value?.querySelectorAll('.progress')[index] as HTMLElement) || null
    if (container) {
      const bar = new ProgressBar.Circle(container, {
    color: '#aaa',
    trailColor: '#000000',
    strokeWidth: 6,
    trailWidth: 6,
    easing: 'easeInOut',
    duration: 1400,
    text: {
        autoStyleContainer: false,
    },
    from: { color: '#FFC107', width: 6 },
    to: { color: '#FFC107', width: 6 },
    step: function(state, circle) {
        circle.path.setAttribute('stroke', state.color);
        circle.path.setAttribute('stroke-width', state.width);

        const value = Math.round(circle.value() * 100);
        circle.setText(value === 0 ? '' : `${value}%`);
    }
});

bar.animate(value);

    }
  })
})
const progressData = [
  { progressTitle: 'HTML', progress: 0.9, color: '#FFC107' },
  { progressTitle: 'CSS', progress: 0.95, color: '#FFC107' },
  { progressTitle: 'JS', progress: 0.75, color: '#FFC107' },
  { progressTitle: 'PHP', progress: 0.65, color: '#FFC107' },
  { progressTitle: 'WordPress', progress: 0.85, color: '#FFC107' }
];
onMounted(() => {
  const wrappers = document.querySelectorAll('.progress-wrapper');

  wrappers.forEach((wrapper, index) => {
    const container = wrapper.querySelector('.progress-container');
    const percentageLabel = wrapper.querySelector('.percentage');
    const { progress, color } = progressData[index];

    if (container && percentageLabel) {
      new ProgressBar.Line(container, {
        strokeWidth: 2,
        easing: 'easeInOut',
        duration: 1400,
        color: color,
        trailColor: '#000',
        trailWidth: 8,
        svgStyle: { width: '100%', height: '100%' },
        text: {
          style: {
            color: 'transparent',
          },
          autoStyleContainer: false
        },
        from: { color: color },
        to: { color: '#ED6A5A' },
        step: (state, bar) => {
          percentageLabel.textContent = Math.round(bar.value() * 100) + ' %';
        }
      }).animate(progress);
    }
  });
});


</script>

<template>
  <aside
    class="absolute left-0 top-0 z-30 flex h-[940px] w-72.5 flex-col overflow-hidden bg-[#20202a] duration-300 ease-linear dark:bg-boxdark lg:static lg:translate-x-0"
    :class="{
      'translate-x-0': sidebarStore.isSidebarOpen,
      '-translate-x-full': !sidebarStore.isSidebarOpen
    }"
    ref="target"
  >
    <!-- SIDEBAR HEADER -->
    <div class="sticky top-0 bg-[#252532] w-full flex p-8 justify-center items-center text-center z-10">
      <div>
        <div class="w-22 h-22 group mx-auto relative mb-2">
          <img src="@/assets/images/logo/Frontendface-1.jpg" class="rounded-full w-full  h-full" alt="Logo" />
          <div class="absolute  bottom-0 right-2 bg-yellow-500 w-4 h-4 rounded-full">
            <div class="animate-ping h-full w-full rounded-full bg-yellow-400 opacity-75"></div>
            <p class="absolute -top-1 opacity-0 duration-500 group-hover:opacity-100 group-hover:translate-x-0 left-9 text-xs translate-x-10 py-1 px-1 bg-[#191923]">
              Available
              <span class="w-4 rotate-45 -z-30 -left-1 h-4 absolute bg-[#191923]"></span>
            </p>
          </div>
        </div>
        <div class="pb-2">
          <h3 class="text-white text-sm mb-[10px] font-semibold">Aurtur Cater</h3>
          <p class="text-gray-400 text-xs">Front-end Developer</p>
          <p class="text-gray-400 text-xs">UX/UI Designer</p>
        </div>
        <button class="block absolute top-0 right-0 p-4 lg:hidden" @click="sidebarStore.isSidebarOpen = false">
        <svg
          class="fill-current"
          width="20"
          height="18"
          viewBox="0 0 20 18"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M19 8.175H2.98748L9.36248 1.6875C9.69998 1.35 9.69998 0.825 9.36248 0.4875C9.02498 0.15 8.49998 0.15 8.16248 0.4875L0.399976 8.3625C0.0624756 8.7 0.0624756 9.225 0.399976 9.5625L8.16248 17.4375C8.31248 17.5875 8.53748 17.7 8.76248 17.7C8.98748 17.7 9.17498 17.625 9.36248 17.475C9.69998 17.1375 9.69998 16.6125 9.36248 16.275L3.02498 9.8625H19C19.45 9.8625 19.825 9.4875 19.825 9.0375C19.825 8.55 19.45 8.175 19 8.175Z"
            fill=""
          />
        </svg>
      </button>
      </div>
    </div>
    <!-- SIDEBAR HEADER -->
    <!-- SIDEBAR CONTENT -->
    <div class="p-4">
      <ul class="pb-4">
        <li class="flex justify-between">
          <h3 class="text-white text-sm font-semibold">Residence:</h3>
          <span class="text-sm">Canada</span>
        </li>
        <li class="flex justify-between py-1">
          <h3 class="text-white text-sm font-semibold">City:</h3>
          <span class="text-sm">Toronto</span>
        </li>
        <li class="flex justify-between">
          <h3 class="text-white text-sm font-semibold">Age:</h3>
          <span class="text-sm">26</span>
        </li>
      </ul>
      <div class="w-full h-px bg-[#646466] opacity-30"></div>
      <div class="flex justify-around items-center pt-7 pb-3">
        <div v-for="(value, index) in progressValues" :key="index" class="text-center mb-4">
          <div class="progress"></div>
          <p class="mt-2 text-white text-xs">{{ labels[index] }}</p>
        </div>
      </div>
  <div class="w-full h-px bg-[#646466] mb-7 opacity-30"></div>
      <div id="progress-bars">
          <div class="progress-wrapper" v-for="(item, index) in progressData" :key="index">
            <div class="progress-info pb-1">
              <div class="progress-label">{{ item.progressTitle }}</div>
              <div class="percentage"></div>
            </div>
            <div class="progress-container"></div>
          </div>
        </div>
        <div class="w-full h-px bg-[#646466] opacity-30"></div>
        <div class="pt-4">
          <ul class="pb-4">
            <li class="flex items-center gap-2 text-sm">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-3 text-[#FFC107]">
                  <path fill-rule="evenodd" d="M19.916 4.626a.75.75 0 0 1 .208 1.04l-9 13.5a.75.75 0 0 1-1.154.114l-6-6a.75.75 0 0 1 1.06-1.06l5.353 5.353 8.493-12.74a.75.75 0 0 1 1.04-.207Z" clip-rule="evenodd" />
              </svg>

              <span>Boostrap, Materialize</span>
            </li>
            <li class="flex items-center gap-2 text-sm">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-3 text-[#FFC107]">
                  <path fill-rule="evenodd" d="M19.916 4.626a.75.75 0 0 1 .208 1.04l-9 13.5a.75.75 0 0 1-1.154.114l-6-6a.75.75 0 0 1 1.06-1.06l5.353 5.353 8.493-12.74a.75.75 0 0 1 1.04-.207Z" clip-rule="evenodd" />
              </svg>

              <span>Stylus, Sass, Less</span>
            </li>
            <li class="flex items-center gap-2 text-sm">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-3 text-[#FFC107]">
                  <path fill-rule="evenodd" d="M19.916 4.626a.75.75 0 0 1 .208 1.04l-9 13.5a.75.75 0 0 1-1.154.114l-6-6a.75.75 0 0 1 1.06-1.06l5.353 5.353 8.493-12.74a.75.75 0 0 1 1.04-.207Z" clip-rule="evenodd" />
              </svg>

              <span>Gulp, Webpack, Grunt</span>
            </li>
          <li class="flex items-center gap-2 text-sm">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-3 text-[#FFC107]">
                  <path fill-rule="evenodd" d="M19.916 4.626a.75.75 0 0 1 .208 1.04l-9 13.5a.75.75 0 0 1-1.154.114l-6-6a.75.75 0 0 1 1.06-1.06l5.353 5.353 8.493-12.74a.75.75 0 0 1 1.04-.207Z" clip-rule="evenodd" />
              </svg>

              <span>GIT knowledge</span>
          </li>
          </ul>
          <div class="w-full h-px bg-[#646466] opacity-30"></div>
        </div>
        <button class="text-[10px] pt-4 text-start font-semibold flex items-center gap-2">
          DOWNLOAD CV
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-3">
              <path fill-rule="evenodd" d="M12 2.25a.75.75 0 0 1 .75.75v16.19l6.22-6.22a.75.75 0 1 1 1.06 1.06l-7.5 7.5a.75.75 0 0 1-1.06 0l-7.5-7.5a.75.75 0 1 1 1.06-1.06l6.22 6.22V3a.75.75 0 0 1 .75-.75Z" clip-rule="evenodd" />
          </svg>

        </button>
      </div>
    <!-- SIDEBAR CONTENT -->

    <!-- SIDEBAR FOOTER -->
     <div class="bg-[#252532] sticky h-full">
        <ul class="flex justify-between h-full items-center px-8">
          <li>
            <a href="#">
              <svg xmlns="http://www.w3.org/2000/svg" class="size-4 duration-300 hover:text-white" viewBox="0 0 576 512">
                  <path class="fill-current" d="M232 237.2c31.8-15.2 48.4-38.2 48.4-74 0-70.6-52.6-87.8-113.3-87.8H0v354.4h171.8c64.4 0 124.9-30.9 124.9-102.9 0-44.5-21.1-77.4-64.7-89.7zM77.9 135.9H151c28.1 0 53.4 7.9 53.4 40.5 0 30.1-19.7 42.2-47.5 42.2h-79v-82.7zm83.3 233.7H77.9V272h84.9c34.3 0 56 14.3 56 50.6 0 35.8-25.9 47-57.6 47zm358.5-240.7H376V94h143.7v34.9zM576 305.2c0-75.9-44.4-139.2-124.9-139.2-78.2 0-131.3 58.8-131.3 135.8 0 79.9 50.3 134.7 131.3 134.7 61.3 0 101-27.6 120.1-86.3H509c-6.7 21.9-34.3 33.5-55.7 33.5-41.3 0-63-24.2-63-65.3h185.1c.3-4.2 .6-8.7 .6-13.2zM390.4 274c2.3-33.7 24.7-54.8 58.5-54.8 35.4 0 53.2 20.8 56.2 54.8H390.4z"/>
              </svg>
            </a>
          </li>
          <li>
            <a href="#">
              <svg xmlns="http://www.w3.org/2000/svg" class="size-4 duration-300 hover:text-white" viewBox="0 0 512 512">
                  <path class="fill-current" d="M256 8C119.3 8 8 119.3 8 256s111.3 248 248 248 248-111.3 248-248S392.7 8 256 8zm164 114.4c29.5 36 47.4 82 47.8 132-7-1.5-77-15.7-147.5-6.8-5.8-14-11.2-26.4-18.6-41.6 78.3-32 113.8-77.5 118.3-83.5zM396.4 97.9c-3.8 5.4-35.7 48.3-111 76.5-34.7-63.8-73.2-116.2-79-124 67.2-16.2 138 1.3 190.1 47.5zm-230.5-33.3c5.6 7.7 43.4 60.1 78.5 122.5-99.1 26.3-186.4 25.9-195.8 25.8C62.4 147.2 106.7 92.6 165.9 64.6zM44.2 256.3c0-2.2 0-4.3 .1-6.5 9.3 .2 111.9 1.5 217.7-30.1 6.1 11.9 11.9 23.9 17.2 35.9-76.6 21.6-146.2 83.5-180.5 142.3C64.8 360.4 44.2 310.7 44.2 256.3zm81.8 167.1c22.1-45.2 82.2-103.6 167.6-132.8 29.7 77.3 42 142.1 45.2 160.6-68.1 29-150 21.1-212.8-27.9zm248.4 8.5c-2.2-12.9-13.4-74.9-41.2-151 66.4-10.6 124.7 6.8 131.9 9.1-9.4 58.9-43.3 109.8-90.8 142z"/>
              </svg>

            </a>
          </li>
          <li>
            <a href="#">
              <svg xmlns="http://www.w3.org/2000/svg" class="size-4 duration-300 hover:text-white" viewBox="0 0 496 512">
                <path class="fill-current" d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3 .3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5 .3-6.2 2.3zm44.2-1.7c-2.9 .7-4.9 2.6-4.6 4.9 .3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3 .7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3 .3 2.9 2.3 3.9 1.6 1 3.6 .7 4.3-.7 .7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3 .7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3 .7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z"/>
              </svg>

            </a>
          </li>
          <li>
            <a href="#">
              <svg xmlns="http://www.w3.org/2000/svg" class="size-4 duration-300 hover:text-white" viewBox="0 0 512 512">
                <path class="fill-current" d="M459.4 151.7c.3 4.5 .3 9.1 .3 13.6 0 138.7-105.6 298.6-298.6 298.6-59.5 0-114.7-17.2-161.1-47.1 8.4 1 16.6 1.3 25.3 1.3 49.1 0 94.2-16.6 130.3-44.8-46.1-1-84.8-31.2-98.1-72.8 6.5 1 13 1.6 19.8 1.6 9.4 0 18.8-1.3 27.6-3.6-48.1-9.7-84.1-52-84.1-103v-1.3c14 7.8 30.2 12.7 47.4 13.3-28.3-18.8-46.8-51-46.8-87.4 0-19.5 5.2-37.4 14.3-53 51.7 63.7 129.3 105.3 216.4 109.8-1.6-7.8-2.6-15.9-2.6-24 0-57.8 46.8-104.9 104.9-104.9 30.2 0 57.5 12.7 76.7 33.1 23.7-4.5 46.5-13.3 66.6-25.3-7.8 24.4-24.4 44.8-46.1 57.8 21.1-2.3 41.6-8.1 60.4-16.2-14.3 20.8-32.2 39.3-52.6 54.3z"/>
              </svg>

            </a>
          </li>
          <li>
            <a href="#">
              <svg xmlns="http://www.w3.org/2000/svg" class="size-4 duration-300 hover:text-white" viewBox="0 0 448 512">
                  <path class="fill-current" d="M100.3 448H7V149.7h93.3V448zM53.7 108.1C24 108.1 0 84.1 0 54.3 0 24.3 24.3 0 53.7 0s53.7 24 53.7 54.3c-.1 29.8-24.3 53.8-53.7 53.8zm394.3 339.9h-93.1V302.4c0-34.7-12.4-58.4-43.5-58.4-23.7 0-37.7 16-43.9 31.4-2.2 5.4-2.7 12.9-2.7 20.5v152.1H171V149.7h89.4v40.8c11.8-18.2 33.1-44.1 80.5-44.1 58.7 0 102.8 38.3 102.8 120.7V448z"/>
              </svg>

            </a>
          </li>
        </ul>
     </div>
    <!-- SIDEBAR FOOTER -->
  </aside>
</template>

<style scoped>
.progress {
  width: 50px;
  height: 50px;
  position: relative;
  font-size: 11px !important;
}
.progress-wrapper {
  margin-bottom: 15px;
  position: relative;
}
.progress-container {
  width: 100%;
  height: 4px; 
  position: relative;
}
.progress-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 11px;
  color: #999;

}
</style>
