<script setup>
import { useRoute } from 'vue-router'
import { galleryItems } from '~/store/gallery'

const route = useRoute()
const project = galleryItems.find((item) => item.slug === route.params.slug)
</script>

<template>
  <div v-if="project" class="py-24">
    <div class="container mx-auto px-6">
      <h1 class="text-5xl font-bold text-brand-dark-blue text-center">
        {{ project.title }}
      </h1>
      <img :src="project.src" :alt="project.title" class="mt-8 w-full h-auto rounded-lg shadow-lg" />
      <div class="mt-8 text-lg text-gray-700">
        <p>
          This is a simple project detail page for
          <span class="font-bold">{{ project.title }}</span
          >. The project has a description of
          <span class="font-bold">{{ project.description }}</span
          >.
        </p>
        <p class="mt-4">
          Further details about the project can be added here, such as the scope of
          work, challenges, and solutions.
        </p>
      </div>
    </div>
  </div>
  <div v-else class="py-24 text-center">
    <h1 class="text-4xl font-bold text-brand-dark-blue">Project not found</h1>
  </div>
</template>
