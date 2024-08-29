<script setup>
import { ref } from 'vue'
import ServiceCard from '../../components/Card/SeriveCard.vue'


const data = ref([
  {
    title: 'Web Development',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
  },
  {
    title: 'UI/UX Design',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
  },
  {
    title: 'Sound Design',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
  },
  {
    title: 'Game Design',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
  },
  {
    title: 'Advertising',
    des: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse commodi deserunt vitae, vero quasi! Veniam quaerat tenetur pariatur doloribus.',
  },
])
</script>

<template>
  <section>
    <h2 class="text-lg font-semibold text-white py-7 text-center lg:text-left">My Services</h2>
  
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-7">

    <service-card

      v-for="(item, index) in data"

      :key="index"

      :title="item.title"

      :des="item.des"

    />

  </div>
  </section>
</template>