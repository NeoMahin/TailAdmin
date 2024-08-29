<script setup lang="ts">
import FrontendHeaderArea from '@/components/Header/FrontendHeaderArea.vue'
import FrontendSidebarArea from '@/components/Sidebar/FrontendSidebarArea.vue'
</script>

<template>
  <!-- ===== Page Wrapper Start ===== -->
  <div class="flex h-screen container p-4 overflow-hidden ">
    <!-- ===== Sidebar Start ===== -->
    <FrontendSidebarArea />
    <!-- ===== Sidebar End ===== -->

    <!-- ===== Content Area Start ===== -->
    <div class="relative flex flex-1 flex-col overflow-y-auto overflow-x-hidden customScroll">
      <!-- ===== Header Start ===== -->
      <FrontendHeaderArea />
      <!-- ===== Header End ===== -->

      <!-- ===== Main Content Start ===== -->
      <main>
        <div class="mx-auto max-w-screen-2xl">
          <slot></slot>
        </div>
      </main>
      <!-- ===== Main Content End ===== -->
    </div>
  </div>
  <!-- ===== Page Wrapper End ===== -->
</template>
