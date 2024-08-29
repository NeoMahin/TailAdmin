<script setup>
import InputCom from '../../../components/Input/Input.vue'
import textArea from '../../../components/Input/textArea.vue'
import ButtonSubmit from '../../../components/Buttons/ButtonSubmit.vue'



</script>



<template>
  <section>
    <h2 class="text-lg font-semibold text-center lg:text-left text-white py-7">Get in touch</h2>
    <div class="bg-[#252532] w-full p-7 grid grid-cols-1 gap-7">
      <div>
          <input-com placeholder="Name">
            <template v-slot:icon>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="currentColor"
                class="size-4 text-white"
              >
                <path
                  fill-rule="evenodd"
                  d="M7.5 6a4.5 4.5 0 1 1 9 0 4.5 4.5 0 0 1-9 0ZM3.751 20.105a8.25 8.25 0 0 1 16.498 0 .75.75 0 0 1-.437.695A18.683 18.683 0 0 1 12 22.5c-2.786 0-5.433-.608-7.812-1.7a.75.75 0 0 1-.437-.695Z"
                  clip-rule="evenodd"
                />
              </svg>
            </template>
          </input-com>
      </div>
      <div>
          <input-com placeholder="Your Email" type="email">
            <template v-slot:icon>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="currentColor"
                class="size-4 text-white"
              >
                <path
                  fill-rule="evenodd"
                  d="M17.834 6.166a8.25 8.25 0 1 0 0 11.668.75.75 0 0 1 1.06 1.06c-3.807 3.808-9.98 3.808-13.788 0-3.808-3.807-3.808-9.98 0-13.788 3.807-3.808 9.98-3.808 13.788 0A9.722 9.722 0 0 1 21.75 12c0 .975-.296 1.887-.809 2.571-.514.685-1.28 1.179-2.191 1.179-.904 0-1.666-.487-2.18-1.164a5.25 5.25 0 1 1-.82-6.26V8.25a.75.75 0 0 1 1.5 0V12c0 .682.208 1.27.509 1.671.3.401.659.579.991.579.332 0 .69-.178.991-.579.3-.4.509-.99.509-1.671a8.222 8.222 0 0 0-2.416-5.834ZM15.75 12a3.75 3.75 0 1 0-7.5 0 3.75 3.75 0 0 0 7.5 0Z"
                  clip-rule="evenodd"
                />
              </svg>
            </template>
          </input-com>
      </div>
      <div>
          <text-area class="text-xs" placeholder='Massege'>
              <template v-slot:icon>
          
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 24 24"
                    fill="currentColor"
                    class="size-4 text-white"
                  >
                    <path
                      d="M1.5 8.67v8.58a3 3 0 0 0 3 3h15a3 3 0 0 0 3-3V8.67l-8.928 5.493a3 3 0 0 1-3.144 0L1.5 8.67Z"
                    />
                    <path
                      d="M22.5 6.908V6.75a3 3 0 0 0-3-3h-15a3 3 0 0 0-3 3v.158l9.714 5.978a1.5 1.5 0 0 0 1.572 0L22.5 6.908Z"
                    />
                  </svg>
              </template>
          </text-area>
      </div>
      <div>
  
          <button-submit passedClass="bg-yellow-500 px-12 py-4 text-black font-semibold text-sm" type='submit'>
              Send massege
          </button-submit>
      </div>
  </div>
  </section>
</template>