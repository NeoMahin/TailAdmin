<script setup lang="ts">
const PriceData = [
  {
    id: 1,
    title: 'Starter Price',
    price: 'Free',
    services: [
      { label: 'UI design', isAvailable: true },
      { label: 'Web Development', isAvailable: true },
      { label: 'Logo design', isAvailable: false },
      { label: 'SEO optimization', isAvailable: false },
      { label: 'Wordpress integration', isAvailable: false }
    ],
    link: '#'
  },
  {
    id: 2,
    title: 'Hourly payment',
    price: '29h',
    services: [
      { label: 'UI design', isAvailable: true },
      { label: 'Web Development', isAvailable: true },
      { label: 'Logo design', isAvailable: true },
      { label: 'SEO optimization', isAvailable: false },
      { label: 'Wordpress integration', isAvailable: false }
    ],
    link: '#'
  },
  {
    id: 3,
    title: 'Full time',
    price: '2999m',
    services: [
      { label: 'UI design', isAvailable: true },
      { label: 'Web Development', isAvailable: true },
      { label: 'Logo design', isAvailable: true },
      { label: 'SEO optimization', isAvailable: true },
      { label: 'Wordpress integration', isAvailable: true }
    ],
    link: '#'
  }
]
</script>

<template>
  <section>
    <h2 class="text-lg font-semibold text-white py-7 text-center lg:text-left">Price Plans</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-7">
      <div
        v-for="priceOption in PriceData"
        :key="priceOption.id"
        class="bg-[#252532] px-4 shadow-lg overflow-hidden"
      >
        <div class="p-6 text-center">
          <h2 class="text-xl text-white font-semibold mb-2">{{ priceOption.title }}</h2>
          <p class="text-yellow-500 py-4 text-3xl font-bold mb-4">
            <span v-if="priceOption.price !== 'Free'" class="xs">$</span>
            {{ priceOption.price }}
          </p>
          <ul class="mb-4">
            <li
              class="flex items-center justify-center gap-2 mb-2 font-medium text-sm"
              v-for="service in priceOption.services"
              :key="service.label"
              :class="service.isAvailable ? 'text-white' : 'text-gray-500'"
            >
              <span v-if="service.isAvailable">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="currentColor"
                  class="size-3 text-yellow-500"
                >
                  <path
                    fill-rule="evenodd"
                    d="M19.916 4.626a.75.75 0 0 1 .208 1.04l-9 13.5a.75.75 0 0 1-1.154.114l-6-6a.75.75 0 0 1 1.06-1.06l5.353 5.353 8.493-12.74a.75.75 0 0 1 1.04-.207Z"
                    clip-rule="evenodd"
                  />
                </svg>
              </span>
              <span v-else>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="currentColor"
                  class="size-3 text-yellow-500"
                >
                  <path
                    fill-rule="evenodd"
                    d="M4.293 4.293a1 1 0 0 1 1.414 0L12 10.586l6.293-6.293a1 1 0 0 1 1.414 1.414L13.414 12l6.293 6.293a1 1 0 0 1-1.414 1.414L12 13.414l-6.293 6.293a1 1 0 0 1-1.414-1.414L10.586 12 4.293 5.707a1 1 0 0 1 0-1.414Z"
                    clip-rule="evenodd"
                  />
                </svg>
              </span>
              <span>
                {{ service.label }}
              </span>
            </li>
          </ul>
          <div class="flex items-center justify-center">
            <a
              :href="priceOption.link"
              class="py-3 bg-transparent text-sm text-yellow-500 font-semibold"
            >
              Ordere Now
            </a>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="currentColor"
              class="size-5 pt-1 text-yellow-500"
            >
              <path
                fill-rule="evenodd"
                d="M16.28 11.47a.75.75 0 0 1 0 1.06l-7.5 7.5a.75.75 0 0 1-1.06-1.06L14.69 12 7.72 5.03a.75.75 0 0 1 1.06-1.06l7.5 7.5Z"
                clip-rule="evenodd"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
