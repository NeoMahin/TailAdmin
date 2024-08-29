<script setup>
import { ref } from 'vue';

defineProps({
  id: String,
  type: String,
  value: String,
  placeholder: String,
  disabled: Boolean,
  passedClass: String,
});

const isFocused = ref(false);

const onFocus = () => {
  isFocused.value = true;
};

const onBlur = () => {
  isFocused.value = false;
};
</script>

<template>
  <form>
    <div class="flex">
      <div 
        :class="[
          'icon-container px-4 pt-5 transition-colors duration-500', 
          { 
            'bg-yellow-500': isFocused, 
            'bg-[#191923]': !isFocused 
          }
        ]" 
        v-if="$slots.icon"
      >
        <slot name="icon"></slot>
      </div>

      <div 
        class="bg-[#191923] px-2 pt-2 icon-container transition-colors duration-500" 
        v-else
        :class="{ 'bg-yellow-500': isFocused }"
      >
        Default
      </div>
      
      <div class="w-full">
        <input
          class="px-2 py-4 w-full outline-none bg-[#20202a]"
          :id="id"
          :type="type"
          :value="value"
          @input="$emit('input', $event.target.value)"
          :placeholder="placeholder"
          :disabled="disabled"
          :class="passedClass"
          @focus="onFocus"
          @blur="onBlur"
        />
      </div>
    </div>
  </form>
</template>

<style scoped>
.icon-container {
  transition: background-color 0.5s ease;
}

input,
input::placeholder {
    font-size: 14px;
}
</style>
