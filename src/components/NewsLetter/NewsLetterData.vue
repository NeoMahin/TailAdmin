<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/swiper-bundle.css'
import 'swiper/css/navigation';
import { Navigation } from 'swiper/modules'
import NewsLetter from '../../components/NewsLetter/NewsLetter.vue'

const data = ref([
  {
    title: 'Paul Trueman',
    subTitle: 'Template author',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/1.jpg',
  },
  {
    title: 'John Doe',
    subTitle: 'Software Engineer',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/4.jpg',
  },
  {
    title: 'Jane Smith',
    subTitle: 'Product Manager',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/3.jpg',
  },
  {
    title: 'Jane Smith',
    subTitle: 'Product Manager',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/1.jpg',
  },
])

const modules = ref([Navigation])
</script>

<template>
  <section>
    <h2 class="text-lg font-semibold text-white py-7 text-center lg:text-left">Newsletter</h2>
    <Swiper
    class="custom-swiper"
      :navigation="true"
      :modules="modules"
      :slides-per-view="1"
      :space-between="10"
      :breakpoints="{
        640: { slidesPerView: 1, spaceBetween: 10 },
        768: { slidesPerView: 2, spaceBetween: 20 },
        1024: { slidesPerView: 2, spaceBetween: 30 },
        1280: { slidesPerView: 3, spaceBetween: 30 },
      }"
    >
      <SwiperSlide
        v-for="(item, index) in data"
        :key="index"
      >
        <NewsLetter
          :title="item.title"
          :subTitle="item.subTitle"
          :des="item.des"
          :imgSrc="item?.imgSrc"
        />
      </SwiperSlide>
    </Swiper>
  </section>
</template>
