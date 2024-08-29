<script setup lang="ts">
const props = defineProps({
  type: String,
  passedClass: String,
  disabled: Boolean
})
</script>

<template>
  <button
    :type="type"
    :class="passedClass"
    :disabled="disabled"
  >
    <slot name="icon"></slot>
    <slot></slot>
  </button>
</template>
