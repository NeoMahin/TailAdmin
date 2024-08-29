<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  buttonText: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="flex items-center">
    <a href=":;" class="bg-transparent text-xs text-yellow-500 font-semibold">
      {{ buttonText }}
    </a>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      fill="currentColor"
      class="size-4 pt-1 text-yellow-500"
    >
      <path
        fill-rule="evenodd"
        d="M16.28 11.47a.75.75 0 0 1 0 1.06l-7.5 7.5a.75.75 0 0 1-1.06-1.06L14.69 12 7.72 5.03a.75.75 0 0 1 1.06-1.06l7.5 7.5Z"
        clip-rule="evenodd"
      />
    </svg>
  </div>
</template>
