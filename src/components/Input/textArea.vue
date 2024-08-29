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
    <div class="flex">
      <div 
        class="px-4 pt-3 transition-colors duration-300"
        :class="{
          'bg-yellow-500': isFocused,
          'bg-[#191923]': !isFocused
        }"
        v-if="$slots.icon"
      >
        <slot 
          name="icon" 
          :class="{
            'text-black': isFocused,
            'text-white': !isFocused
          }"
        ></slot>
      </div>

      <div 
        class="bg-[#191923] p-2 transition-colors duration-300"
        v-else
        :class="{ 'bg-yellow-500': isFocused }"
      >
        Default
      </div>
      
      <div class="w-full">
        <textarea 
          class="w-full h-40 p-2 outline-none bg-[#20202a]"
          :id="id"
          :value="value"
          :placeholder="placeholder"
          :disabled="disabled"
          :class="passedClass"
          @focus="onFocus"
          @blur="onBlur"
        ></textarea>
      </div>
    </div>
 
</template>


<style scoped>

textarea,
textarea::placeholder {
    font-size: 14px;
}
</style>
