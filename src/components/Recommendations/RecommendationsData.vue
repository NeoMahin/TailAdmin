<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/swiper-bundle.css'
import 'swiper/css/navigation';
import { Navigation } from 'swiper/modules'
import RecommendationsSec from './RecommendationsSec.vue'

const data = ref([
  {
    title: 'Paul Trueman',
    subTitle: 'Template author',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/face-1.jpg',
    ratingNum: 3,
  },
  {
    title: 'John Doe',
    subTitle: 'Software Engineer',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/face-2.jpg',
    ratingNum: 5,
  },
  {
    title: 'Jane Smith',
    subTitle: 'Product Manager',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/face-3.jpg',
    ratingNum: 4,
  },
  {
    title: 'Jane Smith',
    subTitle: 'Product Manager',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
    imgSrc: 'src/assets/images/new-user/face-1.jpg',
    ratingNum: 2,
  },
])

const modules = ref([Navigation])
</script>

<template>
  <section>
    <h2 class="text-lg font-semibold text-white py-7 text-center lg:text-left">Recommendations</h2>
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
        <RecommendationsSec
          :title="item.title"
          :subTitle="item.subTitle"
          :des="item.des"
          :imgSrc="item?.imgSrc"
          :ratingNum="item?.ratingNum"
        />
      </SwiperSlide>
    </Swiper>
  </section>
</template>

<style>

  .custom-swiper .swiper-button-next::after,
.custom-swiper .swiper-button-prev::after {
  font-size: 10px;
  color: white;
}
.custom-swiper {
  position: relative;
  overflow: visible;
  display: flex;
  align-items: center;
}

.custom-swiper .swiper-button-next,
.custom-swiper .swiper-button-prev {
  position: absolute;
  top: 100%;
  transform: translateY(70%);
}


.custom-swiper .swiper-button-prev {
  @apply left-[80%] sm:left-[87%] md:left-[89%] lg:left-[91%] xl:left-[93%] 2xl:left-[95%]

}

</style>
