<script setup>
import FrontendButtonDefault from '../../components/Buttons/FrontendButtonDefault.vue';
import { ref, onMounted } from "vue";
import Typed from "typed.js";

// Define your typed.js options
const typedOptions = {
    strings: ["web interface.","ios and android applications.","design mocups.","automation tools."],
    typeSpeed: 100,
    backSpeed: 40,
    backDelay: 1000,
    startDelay: 500,
    loop: true,
};

const typedElement = ref(null);

onMounted(() => {
    if (typedElement.value) {
        new Typed(typedElement.value, typedOptions);
    }
    
});
</script>

<template>
    <section>
        <div class=" relative">
            <div class="w-full relative py-7 lg:px-7">
                <div class="w-[90%] mx-auto h-7 bg-[#1e1e28]"></div>

                <div class="p-7 relative flex items-center leading-tight w-full h-full">
                    <img class="opacity-50 absolute top-0 left-0 w-full h-full object-cover z-0"
                        src="../../assets/images/Background/bg.jpg" alt="">
                    <div class="relative z-10 w-full text-center lg:text-left lg:w-1/2">
                        <h1 class="text-white text-[38px] sm:text-[45px] xl:text-[52px] font-bold">Discover my Amazing Art Space!</h1>
                        <div class="my-6" style="font-family: 'Courier New', monospace;">
                            <span class="text-yellow-500 ">&lt;code&gt;</span>
                            <span class="text-white ">I build </span><span class="text-white " ref="typedElement"></span>
                            <span class="text-yellow-500 ">&lt;/code&gt;</span>
                        </div>
                        <div class="lg:flex justify-center lg:justify-start">
                            <FrontendButtonDefault route="/" label="EXPLORE NOW"
                                customClasses="bg-yellow-500 text-black text-[11px] font-semibold !px-[35px] h-[45px]" />
                            <div class="flex justify-center mt-8 lg:mt-0 items-center">
                                <router-link to="/" class="ml-3 mr-2 text-white font-semibold text-[11px]">Hire
                                    Me</router-link>

                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                    stroke-width="1.5" stroke="currentColor" class="size-4 text-white">
                                    <path stroke-linecap="round" stroke-linejoin="round"
                                        d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
                                </svg>
                            </div>


                        </div>
                    </div>
                    <div class="hidden xl:block">
                        <img src="../../assets/images/Background/face-2.png"
                            class="w-[390px] h-[390px] absolute right-[30px] bottom-0" alt="">
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
