<script setup>
import { ref, onMounted, onBeforeUnmount, computed } from 'vue'
import { useRoute } from 'vue-router'

const isOpen = ref(false)
const isScrolled = ref(false)
const route = useRoute()

const handleScroll = () => {
  isScrolled.value = window.scrollY > 0
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})

const headerTextColor = computed(() => {
  if (isScrolled.value) {
    return 'text-brand-dark-blue'
  }
  return route.path === '/' ? 'text-brand-white' : 'text-brand-dark-blue'
})
</script>

<template>
  <div class="bg-brand-white">
    <header
      :class="{
        'bg-white shadow-lg': isScrolled,
        'bg-transparent': !isScrolled,
      }"
      class="fixed top-0 left-0 right-0 z-50 transition-colors duration-300"
    >
      <div class="container mx-auto px-6 py-4">
        <div class="flex items-center justify-between">
          <div>
            <a href="#" :class="headerTextColor" class="text-3xl font-bold">
              <NuxtImg src="/logo-bj.png" loading="lazy" sizes="10vw sm:5vw md:40px" />
            </a>
          </div>
          <div class="hidden md:flex items-center">
            <nuxt-link
              to="/"
              :class="headerTextColor"
              class="px-4 py-2 rounded hover:bg-brand-maroon hover:text-white"
              active-class="font-bold"
              >Home</nuxt-link
            >
            <nuxt-link
              to="/about"
              :class="headerTextColor"
              class="px-4 py-2 rounded hover:bg-brand-maroon hover:text-white"
              active-class="font-bold"
              >About</nuxt-link
            >
            <nuxt-link
              to="/gallery"
              :class="headerTextColor"
              class="px-4 py-2 rounded hover:bg-brand-maroon hover:text-white"
              active-class="font-bold"
              >Gallery</nuxt-link
            >
            <nuxt-link
              to="/contact"
              :class="headerTextColor"
              class="px-4 py-2 rounded hover:bg-brand-maroon hover:text-white"
              active-class="font-bold"
              >Contact</nuxt-link
            >
          </div>
          <div class="md:hidden flex items-center">
            <button @click="isOpen = !isOpen" :class="headerTextColor" class="focus:outline-none">
              <svg
                class="h-6 w-6"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path v-if="!isOpen" d="M4 6h16M4 12h16M4 18h16"></path>
                <path v-else d="M6 18L18 6M6 6l12 12"></path>
              </svg>
            </button>
          </div>
        </div>
        <div
          :class="isOpen ? 'block' : 'hidden'"
          class="md:hidden bg-brand-dark-blue"
        >
          <nuxt-link
            to="/"
            class="block py-2 px-4 text-sm text-brand-white rounded"
            active-class="bg-brand-maroon font-bold"
            >Home</nuxt-link
          >
          <nuxt-link
            to="/about"
            class="block py-2 px-4 text-sm text-brand-white rounded"
            active-class="bg-brand-maroon font-bold"
            >About</nuxt-link
          >
          <nuxt-link
            to="/gallery"
            class="block py-2 px-4 text-sm text-brand-white rounded"
            active-class="bg-brand-maroon font-bold"
            >Gallery</nuxt-link
          >
          <nuxt-link
            to="/contact"
            class="block py-2 px-4 text-sm text-brand-white rounded"
            active-class="bg-brand-maroon font-bold"
            >Contact</nuxt-link
          >
        </div>
      </div>
    </header>
    <main>
      <slot />
    </main>
    <footer class="bg-brand-dark-blue">
      <div class="container mx-auto px-6 py-4">
        <div class="flex items-center justify-between">
          <div>
            <p class="text-brand-white">&copy; 2025 PT Bayur Jaya. All rights reserved.</p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>
