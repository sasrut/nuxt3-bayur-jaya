<script setup>
import { galleryItems } from '~/store/gallery'
</script>

<template>
  <div class="py-24">
    <div class="container mx-auto px-6">
      <h1 class="text-5xl font-bold text-brand-dark-blue text-center">Our Work</h1>
      <p class="mt-4 text-xl text-gray-700 text-center max-w-3xl mx-auto">
        A showcase of our commitment to quality and excellence.
      </p>
      <div class="mt-16 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <nuxt-link
          v-for="(item, index) in galleryItems"
          :key="index"
          :to="`/project/${item.slug}`"
          class="relative group rounded-lg overflow-hidden shadow-lg"
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
  </div>
</template>
