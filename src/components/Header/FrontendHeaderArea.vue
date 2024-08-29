<script setup lang="ts">
import { useSidebarStore } from '@/stores/sidebar'

const { toggleSidebar } = useSidebarStore()
const sidebarStore = useSidebarStore()
</script>

<template>
  <header
    class="sticky top-0 flex w-full z-30 dark:bg-boxdark dark:drop-shadow-none"
  >
    <div class="flex flex-grow items-center justify-between">
      <div class="flex items-center gap-2 sm:gap-4 lg:hidden">
        <!-- Hamburger Toggle BTN -->
        <button
          v-if="!sidebarStore.isSidebarOpen" 
          class="block rounded-sm bg-[#252532] p-1.5 dark:border-strokedark dark:bg-boxdark lg:hidden"
          @click="
            () => {
              console.log('Toggling Sidebar')
              toggleSidebar()
            }
          "
        >
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6 text-yellow-500"
        :class="{ '!w-full delay-300': !sidebarStore.isSidebarOpen }">
  <path stroke-linecap="round" stroke-linejoin="round" d="M12 6.75a.75.75 0 1 1 0-1.5.75.75 0 0 1 0 1.5ZM12 12.75a.75.75 0 1 1 0-1.5.75.75 0 0 1 0 1.5ZM12 18.75a.75.75 0 1 1 0-1.5.75.75 0 0 1 0 1.5Z" />
</svg>

        </button>
        <!-- Hamburger Toggle BTN -->
      </div>
    </div>
  </header>
</template>
