<script setup>
import { galleryItems } from '~/store/gallery'

// Inject Swiper CDN
useHead({
  link: [
    { rel: 'stylesheet', href: 'https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css' }
  ],
  script: [
    {
      src: 'https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js',
      body: true,
      onload: () => {
        // Initialize when script is loaded
        initSwiper()
      }
    }
  ]
})

const initSwiper = () => {
  // Check if Swiper is already defined (in case of navigation/caching)
  // @ts-ignore
  if (typeof Swiper !== 'undefined') {
    // @ts-ignore
    new Swiper('.gallery-swiper', {
      slidesPerView: 1, // Default (Mobile)
      spaceBetween: 30,
      loop: true,
      pagination: {
        el: '.swiper-pagination',
        clickable: true,
      },
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      // Responsive breakpoints to match your original Grid layout
      breakpoints: {
        // when window width is >= 768px (md)
        768: {
          slidesPerView: 2,
        },
        // when window width is >= 1024px (lg)
        1024: {
          slidesPerView: 3,
        }
      }
    });
  }
}

// Fallback: If navigating back to this page and script is already cached/loaded
onMounted(() => {
  setTimeout(() => {
     // @ts-ignore
    if (typeof Swiper !== 'undefined') initSwiper()
  }, 100)
})
</script>

<template>
  <div class="py-24">
    <div class="container mx-auto px-6">
      <h1 class="text-5xl font-bold text-brand-dark-blue text-center">Our Work</h1>
      <p class="mt-4 text-xl text-gray-700 text-center max-w-3xl mx-auto mb-16">
        A showcase of our commitment to quality and excellence.
      </p>

      <div class="swiper gallery-swiper pb-12">
        <div class="swiper-wrapper">
          <div 
            v-for="(item, index) in galleryItems" 
            :key="index" 
            class="swiper-slide h-80" 
          >
            <nuxt-link
              :to="`/project/${item.slug}`"
              class="relative block w-full h-full group rounded-lg overflow-hidden shadow-lg"
            >
              <img
                :src="item.src"
                alt="Project Image"
                class="w-full h-full object-cover transition-transform duration-300 transform group-hover:scale-110"
              />
              <div
                class="absolute inset-0 bg-black bg-opacity-75 flex flex-col items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <h3 class="text-2xl font-bold text-white">{{ item.title }}</h3>
                <p class="text-white mt-2">{{ item.description }}</p>
              </div>
            </nuxt-link>
          </div>
        </div>

        <div class="swiper-pagination"></div>
        <div class="swiper-button-next"></div>
        <div class="swiper-button-prev"></div>
      </div>

    </div>
  </div>
</template>

<style scoped>
/* Ensure the Swiper container has room for the pagination dots at the bottom */
.gallery-swiper {
  padding-bottom: 50px; 
}

/* Optional: Fix the height of slides so they are uniform */
.swiper-slide {
  height: 400px; /* Adjust this height as needed */
}
</style>