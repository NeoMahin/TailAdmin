<script setup lang="ts">
const props = defineProps(['label', 'route', 'customClasses'])
</script>

<template>
  <router-link
    :to="props.route"
    class=" inline lg:mb-0 lg:flex items-center justify-center py-4 px-10 text-center font-medium hover:bg-opacity-90 lg:px-8"
    :class="props.customClasses"
  >
    <slot></slot>
    {{ props.label }}
  </router-link>
</template>
