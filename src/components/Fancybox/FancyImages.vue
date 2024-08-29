<script setup>
    import FancyBox from './FancyBox.vue';
    import BlogDetails from '../Blog/BlogDetails.vue';
</script>

<template>
    <fancy-box
    :options="{
    Carousel: {
      infinite: false,
    },
  }"
    >
    <div class="grid grid-cols-1 md:grid-cols-3 gap-7">

        <div class="grid gap-7">
    
            <div class="h-auto max-w-full relative overflow-hidden group">
                <a  data-fancybox="gallery" href="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/1.jpg">
                    <img class="w-full bg-cover bg-center h-full opacity-70 hover:opacity-100 duration-300 " src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/1.jpg" alt="">
                </a>
                
                <BlogDetails />
            </div>
            <div class="h-auto max-w-full relative overflow-hidden group">
                <a href="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/4.jpg" data-fancybox="gallery">
                    <img class="w-full bg-cover bg-center h-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/4.jpg" alt="">
                </a>
                <BlogDetails />
            </div>
            <div class="h-auto max-w-full relative overflow-hidden group">
                <a href="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/8.jpg" data-fancybox="gallery">
                    <img class="w-full bg-cover bg-center h-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/8.jpg" alt="">
                </a>
                <BlogDetails />
            </div>
        </div>
        <div class="grid gap-7">
        <div class="h-auto max-w-full relative overflow-hidden group">
            <a href="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/2.jpg" data-fancybox="gallery">
                <img class="h-full w-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/2.jpg" alt="">
            </a>
            <BlogDetails />
        </div>
        <div class="h-auto max-w-full relative overflow-hidden group">
            <a href="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/6.jpg" data-fancybox="gallery">
                <img class="h-full w-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/6.jpg" alt="">
            </a>
            <BlogDetails />
        </div>
    </div>
    <div class="grid gap-7">
        <div class="h-auto max-w-full relative overflow-hidden group">
            <a href="h-full w-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/3.jpg" data-fancybox="gallery">
                <img class="h-full w-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/3.jpg" alt="">
            </a>
            <BlogDetails />
        </div>
        <div class="h-auto max-w-full relative overflow-hidden group">
            <a href="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/5.jpg" data-fancybox="gallery">
                <img class="h-full w-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/5.jpg" alt="">
            </a>
            <BlogDetails />
        </div>
        <div class="h-auto max-w-full relative overflow-hidden group">
            <a href="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/7.jpg" data-fancybox="gallery">
                <img class="h-full w-full opacity-70 hover:opacity-100 duration-300" src="https://miller.bslthemes.com/arter-demo/img/works/thumbnail/7.jpg" alt="">
            </a>
            <BlogDetails />
        </div>
    </div>
    </div>
    
    </fancy-box>
</template>