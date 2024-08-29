<script setup lang="ts">
// import { ref } from 'vue'
import FrontendLayout from '@/layouts/FrontendLayout.vue'
import Banner from '@/components/Banner/Banner.vue'
import Content from '@/components/Content/Content.vue';
// const pageTitle = ref('Home')
</script>

<template>
  <FrontendLayout>
    <div class="mx-auto max-w-7xl ">
      <Banner/>
      <Content />
    </div>
  </FrontendLayout>

</template>
